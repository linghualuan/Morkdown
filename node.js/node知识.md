在node中引入外部模块，要使用`require()`来引入

require('路径')    **注意：若使用相对路径，开头必须使用./或../**

在node中，每一个js文件中的js代码都是独立运行在一个函数中，而不是全局作用域，所以一个模块中的变量和函数无法在里一个模块中访问

exports向外部暴露属性或方法

在全局中有一个全局对象global,他的作用和window类似，在全局中创建的变量都会作为global的属性保存，在全局中创建的函数都会作为global的方法保存

**当node执行模块中的代码时，它会将代码写进下面的函数中**

`function (exports, require, module, __filename, __dirname) {`

​		

`}`

实际上模块中的代码都是包装在一个函数中运行的，并且在函数执行时，同时传递了5个参数：

<u>exports:该对象用来将函数或对象暴露到外部</u>

<u>require:函数，用来引入外部的模块</u>

<u>module：代表的是当前模块自身，exports就是module的属性</u>

__filename:当前模块的完整路径

__dirname:当前模块所在文件夹的完整路径



