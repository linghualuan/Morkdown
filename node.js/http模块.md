### 1.什么是http模块?

##### 		1.1什么是客户端、什么是服务器？

​				**在网络节点中，负责消费资源的电脑，叫做客户端；负责对外提供网络资源的电脑，叫做服务器。**

> http模块是Node.js官方提供的、用来创建Web服务器的模块。通过http模块提供的http.createServer()方法，就能方便的吧一台普通的电脑，变成一台Web吴福气，从而对外提供Web资源服务。

#### 		1.2导入

​				`const http = require('http')`



### 2.服务器相关的概念

####  		2.1 IP地址

​				**IP地址就是互联网上每台计算机的唯一地址，因此IP地址具有唯一性。如果把“个人电脑”比作“一台电话”，name“IP地址”就相当于“电话号码”，只有在知道对方IP地址的前提下，才能与对应的电脑之间进行数据通			信。**

​				**互联网中每台Web服务器，都有自己的IP地址，例如：可以在Windows的终端中运行 ping www.baidu.com 命令，即可查看到百度的服务器的IP地址。**

​				 **在开发期间，自己的电脑既是一台服务器，也是一个客户端，为了方便测试，可以在自己的浏览器中输入127.0.0.1这个IP地址，就能把自己的电脑当做一台服务器进行访问了。**

	2.2域名和域名服务器	

​				**IP地址和域名是一一对应关系，这份对应关系存放在一种叫做域名服务器(DNS)的电脑中。使用者只需通过好记得域名访问对应的服务器即可，对应的转换工作由域名服务器实现。因此，域名服务器就是提供IP地址			 和域名之间的转换服务的服务器。**

	2.3端口号

​				**在一台电脑中，可以成百上千个Web服务。每个Web服务都应一个唯一的端口号。客户端发送过来的网络    			请求，通过端口号，可以被准确地交给对应的Web服务进行处理。**

​				注：在URL中，80端口号可以被忽略，只有80端口号可以被忽略，其他的均不可以省略。每个端口不能被多		   个Web服务占用。

		#### 		2.4创建HTTP
	
					##### 				2.4.1调用http.creatSever()方法

​							`const server = http.createServer()`

				##### 				2.4.2绑定request事件

<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220202201925847.png" alt="image-20220202201925847" style="zoom:80%;" />

##### 			2.4.3启动服务器

![image-20220202203459631](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220202203459631.png)

#### 		2.5req请求对象

​				**只要服务器接收到了客户端的请求，就会调用通过server.on()为服务器绑定的request事件处理函数**![image-20220202210818918](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220202210818918.png)

```
2.6res响应对象
```

![image-20220202211742774](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220202211742774.png)

​				**解决中文乱码：`res.setHeader('Content-Type','text/html; charser=utf-8')`**