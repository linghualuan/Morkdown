# vue开发工具

​		

### 第一个按钮

> ​             **作用：观看组件**

<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211121110440000.png" alt="image-20211121110440000" style="zoom:50%;" />

### 第二个按钮

> ​				**作用：vuex开发工具，记录发生的事件，此事件发生在mutations中，页面上展示的为绿色框触发的事件。**

<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211121110743236.png" alt="image-20211121110743236" style="zoom: 50%;" />





<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211121111219688.png" alt="image-20211121111219688" style="zoom: 80%;" />

**每一个事件后有三个按钮：**

​			1.第一个按钮会合并当前事件以及之前的事件，并且合并进入Base State中

​			2.第二个按钮代表删除此事件，并且在此事件基础上进行的事件也会删除，例如有三个JIA事件，每个事件依次在前一个事件基础上进行，则删除第一个，后两个也会一并删除

​			3.第三个按钮代表时间回到当前点击的事件，即页面显示的数据为当前点击的事件返回的数据

### 第三个按钮

> ​		**观看自定义事件，例如子组件向父组件传递事件、全局事件总线**