<h2>1.</h2>

新建一个文件夹**serve**

<h2>2.</h2>

​			在`serve`文件夹下创建一个`js`文件**app.js**

## 3.

​			初始化node，构建package.json,在serve文件夹下运行**npm init -y**,便会在根目录下得到一个package.json

## 4.

​			引入http模块，此为node自带， `const http = require("http")`

## 5.

​			创建服务，`const serve = http.createServe((req,res)=>{`

​										console.log("hello world");

​								`})`

## 6.

​			监听，`serve.listen(3000,127.0.0.1,function(){`

​									`console.log('服务开启成功')`

​						`})`

## 7.

​			在命令行窗口输入：`node app.js`,即可成功访问服务器