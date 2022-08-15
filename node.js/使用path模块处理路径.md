### 1.什么是path路径模块

> path模块是Node.js官方提供的、用来处理路径的模块，它提供了一系列的方法和属性，用来满足用户对路径的处理需求

​		**path.jion()方法：用来将多个路径片段拼接成一个完整的路径字符串**

​		**path.basename()方法：用来从路径字符串中，将文件名解析出来**

​		**path.extname()方法：用来获取路径中的文件扩展名**

> 导入path模块：const path = require('path');



### 2.拼接文件的路径

```
const path = require('path');

let a = path.join('/a','/b','../','/c','./d')

console.log(a)	//\a\c\d
```



​		在以后引入路径的时候不用再写 `__dirname + 文件路径`，可以写成`let a = path.join(__dirname,文件路径)`，今后凡是涉及到路径拼接的操作，都要使用path.join()方法处理，不要直接使用 + 进行字符串的拼接



### 3.获取文件中的文件名

> 使用path.basename()方法，可以获取文件中的最后一部分，经常通过这个方法获取路径中的文件名

**格式：path.basename(path[.ext])**

```
例如:const fpath = '/a/b/c/inedx.html'

path.basename(fpath)  //index.html
```

可以在path.basename()方法中传递第二个参数，参数为文件的扩展名，如：`.html` , 则只会返回`index`,即会把文件的扩展名删除



### 4.获取文件扩展名

> 语法：path.extname(path)

```
例如：let a = '/a/b/c/index.html'

path.extname(a)	//.html
```

