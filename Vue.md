## VueCli 打包需要配置信息

1. 创建 vue.config.js文件 并添加如下代码

```Vue
module.exports = {
	publicPath: './',
	outputDir: 'dist',
	devServer: {
		proxy: {
			'/api': {
				target: '',
				ws: true,
				changeOrigin: true
			}
		}
	},
}
```

2. 在路由文件修改如下信息：

   ```vue
   删除：mode: 'history',
   修改：base:__dirname,
   ```




## Vue 单页面添加样式

- 在style标签后添加scoped属性

