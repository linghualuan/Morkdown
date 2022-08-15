## 1、项目运行起来的时候，浏览器自动打开

--**package.json**文件

​		"script": {

​				"serve": "vue-cli-service serve **--open**"      //在此处添加**--open**

​		}



## 2、关闭eslint语法校验

**开启eslint语法校验会产生：若是声明一个变量而没有使用，则会报语法错误**

创建**vue.config.js**文件

```
module.exports = {
	lintOnSave: false
}
```



## 3、src文件夹简写方法，配置别名 @

创建**jsconfig.json**文件，配置别名@提示，此后，若是进入src文件夹只需要写@...,不需要再写../../。

配置：

```json
{
    "compilerOptions": {
        "baseUrl": "./",
        "paths": {
            "@/*": ["src/*"]
        }
    },
    "exclude": ["node_modules","dist"]
}
```



