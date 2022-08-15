`node -v` 查看node版本

`npm -v` 查看npm版本

`npm install npm@latest -g` 更新最新版本的npm，-g表示全局安装

`npm i 文件名` (下载文件)

`npm uninstall 文件名` (卸载文件)

更新依赖：`npm undate 文件名`

更换版本：`npm i 文件名@版本号`   如：`npm i jquery@3.2.1`

下载依赖之后自动生成一个文件夹（node_modules）,下载的依赖会存放在这个文件夹里

`import $ from 'jquery'` 在js文件里引入jquery

`npm init -y` ,创建一个package.json文件**(文件夹名称必须要用英文)**

`npm init`配置package.json文件

`npm install 包名 --save`	安装包并添加到依赖中

`npm inatall`	下载当前项目所依赖的包 

`npm remove/r 包名`	删除包

`npm install 包名 -g`	全局安装

淘宝镜像：`npm install -g cnpm --registry=https://registry.npmmirror.com`

