> 依赖包：`jsonwebtoken`和`express-jwt`

​		**jsonwebtoken的用法：**

​				jsonwebtoken表示把用户信息加密为token。

​				jwt.sign(参数一，参数二，参数三)，参数一代表要加密的用户的信息，参数二代表要加密的字符串(自定		义)，参数三代表token可以持续的时间



​				例如：`const tokenStr = jwt.sign({username:userInfo.username},secretKey,{expiresIn:'30s'})`



​		**express-jwt的用法：**

​				express-jwt表示解密用户发送过来的token。



​				例如：`app.use(expressJWT({ secret:secretKey, algorithms:['HS256'] }).unless({path:'/login'}))`

secretKey代表自定义的加密字符串，unless表示不需要token的接口