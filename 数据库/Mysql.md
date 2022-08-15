# Mysql

​		**以管理员身份启动命令窗口**

​		**进入mysql的bin目录下**

​		**net start mysql :启动服务器**

​		**net stop mysql:关闭服务器**

​		**mysql -u root -p:进入数据库**(此时root为用户名)

​		**进入数据库后，使用`show databases` ->回车 -> `;` -> 回车，即可查看数据库的构成。**

​		**使用select * from 数据库.表名 -> 回车 -> `;` -> 回车，即可查看此表里面的数据。**

​		**退出数据库:`exit`**

### 查看用户名

​	进入数据库 --> 输入`select user from mysql.user;` --> 

![image-20220316220916562](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220316220916562.png)





更改用户名和密码：

​		

![img](file:///C:\Users\000\Documents\Tencent Files\461232807\Image\C2C\Image1\3FB391F227E0FB3D56326FF4C211F840.jpg)