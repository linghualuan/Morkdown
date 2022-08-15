### 1、什么是express？

​		**官方给出的概念：Express是基于Node.js平台，快速、开放、极简的Web开发框架**

​		**通俗的理解：Express的作用和Node.js内置的http模块类似，是专门用来创建Web服务器的**

​		**Espress的本质：就是一个npm上的第三方包，提供了快速搭建Web服务器的便捷方法**



### 2、express能做什么？

​		**对于前端程序员来说，最常见的两种服务器，分别是：**

​				**1.Web网站服务器：专门对外提供Web网页资源的服务器**

​				**2.API接口服务器：专门对外提供API接口的服务器**

​		**使用Express，我们可以方便、快速的创建Web网站的服务器或API接口服务器**



### 3、express的创建

```
		const express = require('express');

​		const app = express();

		app.get('/',(req,res)=>{
			//
		})

​		app.listen(80,()=>{

​				console.log('服务开启')

​		})
```

#### 		3.1、请求的方式:

​				**get请求：app.get()**

​				**post请求：app.post()**



#### 		3.2、获取客户端传递的参数

​				**通过req.query可以获取到，默认为空对象。**



#### 		3.3、获取URL中的动态参数

​					**路径中的动态参数需要加冒号，例如`/user/:id`，传递多个参数：`/user/:id/:name`**

​					**通过res.params获取动态参数,默认也是空对象**



### 4、托管静态资源

#### 		4.1、express.sattic()

![image-20220204140849058](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204140849058.png)



#### 		4.2、托管多个静态资源目录

​				**如果要托管多个静态资源目录，只需要多次调用express.static();**

​				**例如：**

```
			app.use(express.static('./public'))

			app.use(express.static('./files'))
```

#### 		4.3、挂载路径前缀

![image-20220204150543034](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204150543034.png)



### 5、中间件

> 中间件，特指业务流程的中间处理环节

#### 				5.1、现实生活的例子

![image-20220204164327060](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204164327060.png)

​				**中间件必须有输入和输出**

#### 				5.2、中间件的调用流程

![image-20220204164823622](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204164823622.png)



#### 				5.3、中间件的格式

![image-20220204165129445](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204165129445.png)

#### 				5.4、next()函数的作用

​				**next()函数时实现过个中间件连续调用的关键，它表示把流转关系交给下一个中间件或路由**



#### 				5.5全局生效的中间件

​				客户端发起的任何请求，到达服务器之后，都会触发的中间件，叫做全局生效的中间件。

​				通过调用app.use(中间件函数)，即可定义一个全局生效的中间件。



#### 				5.6定义全局中间件的简化形式

![image-20220204171507528](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204171507528.png)

#### 				5.6中间件的作用

​				多个中间件之间，共享一份req和res。基于这样的特性，我们可以在上游的中间件中，统一为req或res对象			添加自定义的属性或方法，供下游的中间件或路由进行使用



#### 		5.7局部中间件

​				**不使用app.use()定义的中间件叫做局部中间件**

```
//定义中间件
const demo = function(req,res,next){

  console.log('这是一个中间件');

  next();

}

//使用中间件
app.get('/',demo,(req,res) => {

  res.send('这是路径为/的页面')

})
```

​		**上面定义的中间件只会影响使用的路由，不会对其他路由产生影响。**

​		**路由的参数中，第一个永远是路径，最后一个永远是回调，中间可以写任意多个中间件**

```
app.get('/',mw1,mw2,(req,res) => {})

app.get('/',[mw1,mw2],(req,res) => {})				//两种方式等价
```



#### 		5.8使用中间件的5个注意事项

![image-20220204182401794](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204182401794.png)



### 6、中间件的分类

​		1.应用级别的中间件

​		2.路由级别的中间件

​		3.错误级别的中间件

​		4.Express内置的中间件

​		5.第三方的中间件

#### 		6.1应用级别的中间件

​				**通过app.use()或app.get()或app.post(),绑定到app实例上的中间件，叫做应用级别的中间件。**

#### 		6.2路由级别的中间件

​				**绑定到express.Router()实例上的中间件，叫做路由级别的中间件。它的用法和应用级别中间件没有任何区别。只不过，应用级别的中间件是绑定到app实例上，路由级别的中间件绑定到router实例上。**

#### 		6.3错误级别的中间件

![image-20220204183449560](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204183449560.png)

```
const err = function(err,req,res,next){

  console.log('错误信息为：' + err.message);

}
```

​				**注意：错误中间件一定要定义到所有路由之后**



#### 		6.4、Express内置的中间件

![image-20220204184708791](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204184708791.png)

​				**req.body可以打印客户端发送过来的请求体数据**

#### 		6.5、第三方中间件

![image-20220204202711135](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204202711135.png)

​				**注意：Express内置的express.urlencoded中间件，就是基于body-parse这个第三方中间件进一步封装出来  			的。**

### 7、自定义中间件

#### 		7.1、监听req的data事件

![image-20220204204054138](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204204054138.png)

#### 		7.2监听req的end事件

![image-20220204204334134](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204204334134.png)

#### 		7.3使用querystring模块解析请求体数据

![image-20220204204702870](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204204702870.png)

#### 		7.4、将解析出来的数据对象挂载为req.body

![image-20220204210741714](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204210741714.png)



### 8、编写get接口

​		**路由：**

```
const express = require('express');



const router = express.Router();



router.get('/user',(req,res) => {



  const query = req.query;



  res.send({

​    static:0,

​    msg:'请求成功！',

​    data:{

​      query

​    }

  })

})



module.exports = router;
```



​		**使用：**

```
const express = require('express');



const app = express();



const router = require('./编写get接口/j6')



app.use('/api',router)



app.listen(80,() => {

  console.log('http://localhost');

})
```

