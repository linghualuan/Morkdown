### 1.为什么JavaScript可以在浏览器中运行？

​				每个浏览器都有一个JS解析引擎，待执行的JS代码会在JS解析引擎中执行。

​				不同的浏览器解析引擎不同，其中，Chrome的V8解析引擎性能最好。



### 2.为什么JavaScript可以操作DOM和BOM？

​				浏览器中有DOM API，BOM API, Ajax API。

​				在待执行的js代码中可以调用浏览器提供的API，然后把待执行的js代码交给解析引擎来执行。



### 3.浏览器中的JavaScript运行环境

​				运行环境是指JavaScript正常运行所需要的环境。

​				以Chrome浏览器为例，运行环境中包括V8解析引擎，浏览器内置API(DOM API,BOM API,JS内置对象等)。

​				图解：

<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220201144140077.png" alt="image-20220201144140077" style="zoom:80%;" />



**Node.js是一个基于v8引擎的JavaScript运行环境**



**JavaScript在浏览器中运行即为前端开发，在Node.js中运行即为后端开发**



### 4.Node.js中的JavaScript运行环境

​				Node.js运行环境包括V8引擎，内置API(fs,path,http等)



**注意：在Node.js中无法调用BOM，DOM等浏览器内置API**



### 5.Node.js可以用来做什么？

<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220201145517617.png" alt="image-20220201145517617"  />



### 6.Node.js学习路径

​				JavaScript基础语法 + Node.js内置API(fs,path,http等) + 第三方API模块(express,mysql等)



### 7.Node.js环境的安装

##### 				7.1：LTS版本和Current版本的区别

​								1.LTS版本为长期稳定版，对于追求稳定性的企业级项目来说，推荐安装LTS版本的Node.js

​								2.Current版本为新特性尝鲜版，对于追求尝试新特性的用户来说，推荐安装Current版本的Node.js。						但是，Current版本中可能存在隐藏的Bug或安全漏洞，不推荐企业级项目使用。



### 8.什么是终端？

​				终端 (英文：Terminal) 是专门为开发人员设计的，用于**实现人机交互**的一种方式。

​				window中的终端：cmd终端和PowerShell终端，其中，cmd终端出现的较早，PowerShell终端相对于cmd终		端功能更多

​				终端中的快捷键：

​						1.使用上方向键，可以快速定位到上一次的命令。

​						2.使用Tab建，可以快速补全路径。

​						3.使用esc键，可以快速清空当前已经输入的命令。

​						4.输入cls命令，可以清空命令