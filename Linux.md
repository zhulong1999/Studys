## 系统常用命令

- ```
  grep 搜索文本 指定的文件 列如：grep aa index.php 搜索文件里的文本
  ```

- ```
  du 显示当前路径所有的文件夹 并显示文件大小
  ```

- ```
  date 查看系统时间
  ```

- ```
  df -lh 查看硬盘使用状态
  ```

- ```
  free 内存使用状况
  ```

- ```
  is | grep 文件名称 在当前路径查找文件
  ```

- ```
  find 文件路径 文件名称 查找文件 列入：find /www/wwwroot/ demo.php
  ```

- ```
  man 命令名称 查看命令帮助手册 例如：man ls
  q 退出
  ```

  

## Linux 解压/压缩

1.  .gz后缀解压/压缩方式

   ```Linux
   解压:tar zxvf 压缩包名称
   压缩:tar zcvf 压缩包文件 文件名称
   ```

2. .bz2后缀解压/压缩方式

   ```
   解压:tar jxvf 压缩包名称
   压缩:tar jcvf 压缩包文件 文件名称
   ```

3.  .bz后缀解压/压缩方式

   ```
   解压:tar jxvf 压缩包名称
   压缩:未知
   ```


## Linux 编译安装方式

ps：必须要有 C语言编译工具  gcc -v 查看C语言编译工具版本

1. ./configure 配置相关参数信息

   - ```
     通过 ./configure --help 查看当前配置参数
     ```

2. make 编译生成可执行命令或软件

3. make install 吧生产好的软件安装到指定配置目录

## 关闭防火墙

- ```shell
  service iptables stop|start|restart|status 关闭|打开|重启|状态
  ```

## rpm软件包管理(本地安装)

- ```
  rpm -qa 获取全部已经安装的rpm软件
  ```

- ```
  rpm -qa | grep 包名 查询安装指定的软件包
  ```

- ```
  rpm -e 包名 删除指定的软件 ps：软件名称必须是完整的 可以通过 查找软件包 进行复制名称
  ```

- ```
  rpm -ivh 完整包名 安装指定软件
  ```

## yum软件安装(网上下载安装)

- ```
  yum install google
  ```

  

## 请求网页地址

- ```
  curl -i 域名  PS:也就是PHP类似于CURL
  ```

  