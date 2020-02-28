## URL重写

- Nginx 

  ```
  location / {
      try_files $uri $uri/ /index.php?$query_string;
  }
  ```

- Apache

  > *PS:写在public / .htaccess文件*

  ```
  Options +FollowSymLinks -Indexes
  RewriteEngine On
  
  RewriteCond %{HTTP:Authorization} .
  RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
  
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteRule ^ index.php [L]
  
  ```

  

## 中间件

- 定义一个中间件  *必须

```
php artisan male:middleware 中间件名称
```

1.  创建一个中间件程序 *必须

   ```
   //文件路径 /app/Http/Middleware/定义的中间件文件
    public function handle($request, Closure $next)
       {
       	//如果 age参数是否等于200 则跳转到Home页面
           if ($request->age == 200){
             	return redirect('Home')
           }
           //固定写法 即允许「通过」中间件验证
           return $next($request);
       }
   ```

2. 注册一个中间件 *必须

   ```
   //文件路径 \app\Http\Kernel.php
   protected $routeMiddleware = [
           'demo'=>Demo::class,
       ];
   ```

3. 给路有分配中间件 *必须

   ```
   Route::get('/', function () {
       return view('welcome');
   })->middleware('demo');//demo就是注册中间件 
   ```

## 数据迁移

1. 创建一个迁移文件

   ```
   php artisan make:migration 迁移文件 格式:create_users_table 
   ```

2. 执行一个迁移文件

   ```
   php artisan migrate 
   ```

## 数据填充

1. 创建一个填充文件

   ```
   php artisan make:seeder 填充文件 格式：UsersTableSeeder
   ```

2. 执行一个填充文件

   ```
   php artisan db:seed --class=填充文件 格式：UsersTableSeeder 
   ```

   

## 模型 Model

1. 创建一个model

   ```
   php artisan make:model 模型名称
   ```

#### 模型操作

- 常见设置

  ```
  protected $table = ' '; //表关联
  protected $primaryKey = '';//设置主键
  public $incrementing = false;//指示模型主键是否递增
  public $timestamps = false; //指示是否自动维护时间戳
  ```




## 析构函数

- 可以优先调用方法 须继承使用析构方法的类

  ```
  public function __construct(){}
  ```

  

## 创建自定义公共函数库/公共类

> **PS:创建公共函数和公共类 具体步骤一样**

1. 在app下创建一个functions.php    PS:名字可以随便取

2. 在composer.json下的autoload配置如下

   ```
   "files": [
      "app/functioins.php"   //文件路径
     ]
   ```

3. 最后运行Composer命令

   ```
   composer dump-autoload
   ```

   





