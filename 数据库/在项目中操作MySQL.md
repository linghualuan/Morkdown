### 1.在项目中操作MySQL的步骤

![image-20220206132151212](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206132151212.png)

#### 		1.1安装mysql模块

![image-20220206132305021](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206132305021.png)

#### 		1.2配置mysql模块

![image-20220206132531493](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206132531493.png)



#### 		1.3测试mysql模块能否正常工作

![image-20220206133525821](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206133525821.png)

**若果执行的是select语句，得到的数据是数组。**



### 2、插入数据

![image-20220206134343142](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206134343142.png)

**如果执行的是insert into语句，则返回的是一个对象，使用`results.affectedRows === 1`是否为真判断数据是否插入成功。**

#### 2.1插入语句的快捷方式

![image-20220206135943787](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206135943787.png)



### 3、更新数据

![image-20220206140959428](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206140959428.png)

### 		3.1更新数据的快捷方式

![image-20220206142511766](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206142511766.png)



### 4、删除数据

![image-20220206142847858](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206142847858.png)

#### 		4.1、删除标记

![image-20220206143404673](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220206143404673.png)