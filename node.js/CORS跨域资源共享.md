### 1.什么是CORS?

![image-20220204220506661](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204220506661.png)

### 2.接口跨域问题

​		解决接口跨域问题的方案主要有两种：

​				1.CORS(主流的解决方案，推荐使用)

​				2.JSONP(有缺陷的解决方案，只支持GET请求)



### 3.使用cors中间件解决跨域问题

![image-20220204215056080](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204215056080.png)



### 4.CORS的注意事项

![image-20220204220920319](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204220920319.png)



#### 5.CORS响应头部

#### 		5.1、Access-Control-Allow-Origin

![image-20220204221138643](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204221138643.png)

**如果制定了`Access-Control-Allow-Origin`字段的值为通配符*，表示允许来自任何域的请求。**

**即：`res.setHeader('Access-Control-Allow-Origin','*')`**



#### 		5.2、Access-Control-Allow-Headers

![image-20220204221732479](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204221732479.png)



#### 		5.3Access-Control-Allow-Methods

![image-20220204222017787](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204222017787.png)



### 6CORS请求的分类

![image-20220204222319679](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204222319679.png)



#### 		6.1简单请求

![image-20220204222754571](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204222754571.png)

#### 		6.2预检请求

![image-20220204223857523](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204223857523.png)

#### 		6.3简单请求和预检请求的区别

![image-20220204224552069](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220204224552069.png)