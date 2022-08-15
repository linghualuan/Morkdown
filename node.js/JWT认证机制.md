### 1.了解Session认证的局限性

![image-20220206164032681](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206164032681.png)



### 2.什么是JWT

> JWT(全称：JSON Web Token)是目前最流行的跨域认证解决方案。



### 3、JWT的工作机制

![image-20220206164450912](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206164450912.png)

**总结：用户的信息通过Token字符串的形式，保存到客户端浏览器中。服务器通过还原Token字符串的形式来认证用户的身份**



### 4、JWT的组成部分

![image-20220206164841603](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206164841603.png)

### 		4.1、JWT的三个组成部分

![image-20220206165055688](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206165055688.png)



### 5、JWT的使用方式

![image-20220206165236314](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206165236314.png)



### 6、在Express中使用JWT

#### 		6.1、安装JWT相关的包

![image-20220206165502456](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206165502456.png)

#### 		6.2、导入相关的包

​				使用require方法导入，**express-jwt使用6版本**



#### 		6.3、定义secect

![image-20220206170602466](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206170602466.png)



#### 		6.4、在登录成功后生成jwt字符串

![image-20220206193035674](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206193035674.png)

#### 		6.5、将JWT字符串还原成json对象

![image-20220206193720312](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206193720312.png)

**只要配置成功了 express-jwt 这个中间件，就可以把解析出来的用户信息，挂载到 req.user 属性上。**

注意：目前的新版本需要额外属性，`expressJWT({ secret:secretKey, algorithms:['HS256']})`



```
const express = require('express');



const app = express();



*// const bodyParser = require('body-parser');*



app.use(express.urlencoded({ extended: false }))



*// ---------------------------------------------------------------------------*



const jwt = require('jsonwebtoken');



const expressJWT = require('express-jwt');



const secretKey = 'linghualuan';



app.use(expressJWT({ secret: secretKey, algorithms: ['HS256'] }).unless({path:'/login'}));



*//--------------------------------------------------------------------------------*



app.post('/login',(req,res) => {



  const userInfo = req.body;



  console.log(userInfo.username);



  const tokenStr = jwt.sign({username:userInfo.username},secretKey,{expiresIn:'30s'})



  res.send({

​    token:tokenStr

  })



})



app.get('/getUser',(req,res) => {

  console.log(req.user);

  res.send(req.user)

})



app.use((err,req,res,next) => {

  res.send("错误信息是" + err.message)

})



app.listen(80,() => {

  console.log('服务启动');

})
```

判断token错误：

```
app.use((err,req,res,next) =>{
	if(err.name === 'UnauthorizedError'){
		console.log('token错误')
	}
})
```

