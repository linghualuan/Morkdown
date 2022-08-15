## 1.创建节点

###  				1）.创建元素节点

​						**创建节点的格式为：document.createElement(nodeName);**

​						**例如下面的代码创建了一个由'H1'名称指定的标题元素节点**

​						`var btn = document.ceateElement('H1');`

### 				2）.创建文本节点

​						**创建文本节点的格式为：document.createTextNode(text);**

​						**例如下面的代码创建了一个文本节点**

​						`var txt = document.createTextNode('hello world');`

### 				3）.复制节点

​						**复制节点的格式为：node.cloneNode(deep);**

​						**其中，node代表被复制的节点，deep为一个可选的布尔值类型的参数。如果参数为true，还将递归复制当前节点的所有      子孙节点；如果参数为false，则只复制当前节点。其默认参数为false。**

​					

## 2.元素节点的操作

### 				1）在已有节点后插入

​						**格式为：parent.appendChild(newnode),其中，parent代表允许插入节点的父节点。newnode为需要插入的节点对象参数**

​					**举例代码：**

​					<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207124942837.png" alt="image-20211207124942837" style="zoom: 80%;" />

​					**运行结果：**

​					![image-20211207125146381](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207125146381.png)![image-20211207125202760](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207125202760.png)

### 				2）在已有节点前插入

​					**格式为：parent.insertBefore(newnode,existingnode),其中，parent代表允许插入节点的父元素节点，newnode为需要插入的节点对象，existingnode为在其之前插入新节点的子节点**

​				**举例代码：**

​				<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207130044923.png" alt="image-20211207130044923" style="zoom:80%;" />

### 		3）删除一个节点

​					**格式：parent.removeChild(node),其中，parent代表父节点，node为需要删除的子节点，如果成功删除，则此方法返回被删除的节点，如果失败，则返回null**

​				**举例代码**

​			![image-20211207211329337](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207211329337.png)

### 		4)替换节点

​							**格式为：parent.replaceChild(newnode,oldnode),其中，parent代表允许插入节点的父节点，newnode为需要插					入的新节点对象，这个节点可以是文档中已存在的节点，也可以创建新的节点，oldnode为需要被移除的节点对象**

​			**举例代码**

​			<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207212223514.png" alt="image-20211207212223514" style="zoom:80%;" />

​			

## 3.属性节点操作

> 属性节点操作主要包括属性节点的获取、创建和添加3类

### 		1）获取属性节点

​								**格式：element.getAttributeNode(attributename),其中，element代表当前元素节点，attributename代表						属性名称**

​						**举例代码：**

​						<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207213527317.png" alt="image-20211207213527317" style="zoom:80%;" />

### 		2）创建属性节点

​					**格式为：document.createAttribute(attribute),其中，attribute表示要创建的属性名称**

​					**举例代码：**

​					<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207214045079.png" alt="image-20211207214045079" style="zoom:80%;" />

### 		3)添加属性节点

​					**格式为：element.setAttributeNode(attribute),element代表当前元素节点，attributename为属性名称。如果元素中已经存在指定名称的属性，那么该属性将被新属性替代，如果新属性代替了已有的属性，则返回被替代的属性，否则返回null**

​					**举例代码：**

​					<img src="C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207215017264.png" alt="image-20211207215017264" style="zoom:50%;" />

​					**结果：(分别为第一次单击和第二次单击)**

​					![image-20211207215102172](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207215102172.png)![image-20211207215130093](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20211207215130093.png)