### 1、什么是包？

> Node.js中的**第三方模块**又叫做**包**





### 2、包的来源

> 不同于Node.js中的内置模块与自定义模块，包是由第三方个人或团队开发出来的，免费供所有人使用

**注**：Node.js中的包都是免费且开源的，不需要付费即可免费下载使用





### 3、为什么需要包？

由于Node.js的内置模块仅提供了一些底层的API，导致在基于内置模块进行项目开发时效率很低，

包是基于内置模块封装出来的，提供了更高级、更方便的API，极大的提高了开发效率。

包和内置模块之间的关系，类似于jQuery和浏览器内置API之间的关系。





### 4、npm

		#### 		4.1、初次安装包后多了哪些文件？

​				**初次装包完成后，在项目文件夹下多一个叫做node_modules的文件夹和package-lock.js的配置文件。**

![image-20220203201829426](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203201829426.png)

		#### 		
	
		#### 		4.2、安装指定版本的包

​				**默认情况下，使用npm i 命令安装包的时候，会自动安装最新版本的包。如果需要安装指定版本的包，可以			在包名之后，通过@符号指定具体的版本。**

#### 		

#### 		4.3、包的语义化版本规范

![image-20220203203053674](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203203053674.png)

​				**版本号提升的规则：只要前面的版本号增长了，则后面的版本号归零。**





### 5、包管理配置文件

![image-20220203203452154](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203203452154.png)



#### 		5.1、如何记录项目中安装了哪些包？

![image-20220203203933263](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203203933263.png)

#### 		

#### 		5.2、快捷创建package.json

​				**npm包管理工具提供了一个快捷命令，可以在执行命令时所处的命令中，快速创建package.json这个包管理**

​				命令：`npm init -y`

![image-20220203204423257](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203204423257.png)

#### 

#### 		5.3、dependencies节点![image-20220203204949376](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203204949376.png)

​				**若要一次安装多个包，则只需在相隔包名之间添加空格。**

​				例如：`npm i jquery vue`

​				**可以执行`npm i`一次安装完所有依赖包。**



#### 		5.4、卸载包

​				指令：`npm unistall 包名`，注：uninstall没有简写形式



#### 		5.5、devDependencies节点

![image-20220203210706058](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203210706058.png)

![image-20220203210808354](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203210808354.png)

#### 		

#### 		5.6淘宝NPM镜像服务器				![image-20220203215043876](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203215043876.png)



#### 		5.7、nrm

> 为了更方便的切换下包的镜像源，可以安装nrm这个小工具，利用nrm提供的终端命令，可以快速查看和切换下包的镜像源

![image-20220203215836969](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203215836969.png)





### 6.包的分类

> 两类：全局包和项目包

#### 				6.1项目包

![image-20220203221050630](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203221050630.png)



#### 				6.2全局包

![image-20220203221404048](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203221404048.png)

​				注意：1.只有工具性质的包，才有全局安装的必要性，因为他们提供了好用的终端命令。

​								2.判断某个包是否需要全局安装后才能使用，可以参考官方提供的使用说明即可。



#### 				6.3、i5ting_toc

​				**i5ting_toc是一个可以把md文档转为html页面的小工具。**

![image-20220203222136610](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203222136610.png)



#### 				6.4、规范的包结构

![image-20220203222806915](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203222806915.png)



### 7、开发属于自己的包

		#### 		7.1需要实现的功能

​					1.格式化日期

​					2.转义HTML中的特殊字符

​					3.还原HTML中的特殊字符

#### 		![image-20220203223242433](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203223242433.png)

​		![image-20220203231740989](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203231740989.png)

#### 		7.2初始化包的基本结构

![image-20220203223951007](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203223951007.png)

#### 		7.3编写格式化日期功能

​				**index.js:**

```
//格式化日期
function dateFormat(dtStr){

  const date = new Date(dtStr)



  const y = date.getFullYear();



  const m = padZero(date.getMonth() + 1);



  const d = padZero(date.getDate());



  const hh = padZero(date.getHours());



  const dd = padZero(date.getMinutes());



  const ss = padZero(date.getSeconds());



  return `${y}-${m}-${d} ${hh}:${dd}:${ss}`

}



*//补0函数*
function padZero(a){

  return a>9 ? a : '0'+a

}


//转义html字符串
function htmlEscape(htmlStr){
    return htmlStr.replace(/<|>|"|&/g,(match)=>{
        switch (match) {
            case '<':
                return '&lt'
            case '>':
                return '&gt'
            case '"':
                return '&quot'
            case '&':
                return '&amp'

        }
    })
}


module.exports = {

  dateFormat,
  
  htmlEscape

}
```



#### 		7.4在里一个js文件中使用

```
const demo = require('../itzl-tool')	//自动搜索package.json中的main属性，指向为index.js


const a = demo.dateFormat(new Date())


console.log(a);


const b = '<h1 id="wrap">web前端</h1>'


console.log(demo.htmlEscape(b))
```



#### 	7.5、模块化拆分

​				**1.在itzl-tool文件夹下新建src文件夹**

​				**2.在src文件夹下新建两个文件：dateFormat.js 和 htmlEscape.js**

​				**3.dateFormat.js:**

```
//格式化日期
function dateFormat(dtStr){

  const date = new Date(dtStr)



  const y = date.getFullYear();



  const m = padZero(date.getMonth() + 1);



  const d = padZero(date.getDate());



  const hh = padZero(date.getHours());



  const dd = padZero(date.getMinutes());



  const ss = padZero(date.getSeconds());



  return `${y}-${m}-${d} ${hh}:${dd}:${ss}`

}



*//补0函数*
function padZero(a){

  return a>9 ? a : '0'+a

}


module.exports = {
	dateFormat
}
```

​				**htmlEscape.js:**

```
//转义html字符串
function htmlEscape(htmlStr){
    return htmlStr.replace(/<|>|"|&/g,(match)=>{
        switch (match) {
            case '<':
                return '&lt'
            case '>':
                return '&gt'
            case '"':
                return '&quot'
            case '&':
                return '&amp'

        }
    })

}


module.exports = {
	htmlEscape
}
```

​				**4.index.js**

```
const date = require('./src/dateFormat')


const escape = require('./src/htmlEscape')


module.exports = {

  ...date,

  ...escape

}
```

#### 		7.6编写包的说明文档

![image-20220203234343312](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220203234343312.png)



#### 		7.7发布包

##### 				7.7.1注册账号

##### 				7.7.2登录npm账号

​						注：不是在npm官网登录，是在命令行端口登录，一定要在npm官方服务器中登陆。

​						打开终端，输入`npm login`,根据提示输入用户名，邮箱，密码，以及发送给邮箱的验证码。

##### 				7.7.3把包发布到npm上

​						将终端切换到包的根目录之后，运行npm publish命令，即可将包发布到npm上(注意：包名不能雷同)。

##### 				7.7.4删除包

​						运行npm unpublish 包名 --force 命令，即可从npm删除已发布的包。

​						注意：1.npm unpublish命令只能删除72小时以内发布的包

​										2.npm unpublish删除的包，在24小时内不允许重新发布

​										3.发布包的时候要慎重，尽量不要往npm上发布没有意义的包！
