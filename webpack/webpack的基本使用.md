下载依赖：

>npm i webpack webpack-cli -D





执行`npx webpack 入口文件路径 --mode=development`

--mode=development为开发模式

--mode=production为生产模式





清空上次打包的文件：`clean: true`





.eslintrc文件：配置eslint文件

.eslintignore: 忽略哪些文件检查，里面直接写文件名或目录



依赖：`webpack-dev-server`,监视文件的修改，若按常规方式修改文件，必须重新打包才可使用，使用此依赖之后不需重新打包，

配置：跟mode同级，需要在webpack.config.js文件中配置：

```
devServer: {
	host: "localhost",		//启动服务器域名
	port: "3000",		//启动服务器端口号
	open: true	//是否自动打开服务器
}
```

**注：需要使用`npx webpack serve`指令启动**







提取css成单独文件，原css是在js中解析，网速慢会出现闪屏现象，所以需要把css文件单独抽取出来，使用link引入

下载插件：`npm i -D mini-css-extract-plugin`

在webpack.config.js中引入插件`const MiniCssExtractPlugin = require("mini-css-extract-plugin")`

把css配置中所有的"style-loader"换成MiniCssExtractPlugin.loader