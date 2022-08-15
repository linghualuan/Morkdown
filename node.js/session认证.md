### 1.http协议的无状态性

![image-20220206150006088](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206150006088.png)

 

### 2、如何突破http协议的无状态性

![image-20220206150303062](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206150303062.png)



### 3.什么是cookie?

![image-20220206150819022](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206150819022.png)



### 4、cookie在身份认证中的作用

![image-20220206151237672](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206151237672.png)

![image-20220206151549553](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206151549553.png)



### 5、Cookie不具有安全性 

![image-20220206151829010](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206151829010.png)

**注意：千万不要使用Cookie存储重要且隐私的数据！比如用户的身份信息、密码等。**



### 6.提高身份认证的安全性

![image-20220206152459358](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206152459358.png)



### 7、session认证机制

![image-20220206152836452](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206152836452.png)



### 8、在Express中使用session认证

​		**1.在Express项目中，只需要安装express-session中间件，即可在项目中使用Session认证**

​				`npm i express-session`

​		**2、配置express-session中间件**

![image-20220206153342126](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206153342126.png)

​		**3.向session中存数据**

​				当express-session中间件配置成功后，即可通过req.session来访问和使用session对象，从而存储用户的关键			信息。

​		**4、从session中取数据**

![image-20220206155602763](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206155602763.png)

​		**5、清空session中的数据**

​				调用req.session.destroy()函数，即可清空服务器保存的session信息。

![image-20220206160056597](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206160056597.png)

**只会请空当前用户的session，不会清空所有用户的session**