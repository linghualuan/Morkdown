绑定模板的两种方式：

​		1、`el:'#root'`

​		2、先创建vue实例：

​				1)、const v = new Vue({

​								data:{

​								}

​						})

​				2)、在实例的外面使用`v.$mount("#root")`

Object.keys(对象)：把对象的属性遍历形成一个数组

​	如：

​		person:{name:'张三',age:30,school:'郑州轻工业大学'}

​		Object.keys(person)		//[ 'name', 'age', 'school']



Object.defineProperty(对象,'属性名',{ value:属性值}):设置对象的属性，使用此方法遍历的属性不可遍历，若希望遍历，则可在第三个参数里使用`enumerable:true`。	使用此方法添加的属性也是不可修改的，若希望修改，可在**第三个**参数中添加`writable:true`。使用此方法添加的属性也是不可删除的，若希望删除，可在**第三个**参数中添加`configurable:true`



删除对象的属性的方法`delete person.age`





```
let number = 30;

let person = {
	age:10,
	name:'张三'
}

Object.defineProperty(person,'age',{

		get(){

			return number

		},
		set(value){
			number = value
		}

})
```

**Object.defineProperty中有一个get方法，当读取person中的age属性时，就会触发get方法，且age的值就是number的值**

**Object.defineProperty中有一个set方法，当修改person中的age属性时，就会触发时set方法，且age的值就是number的值**





vue中的时间处理函数有一个默认的event参数，可以使用$event占位，例如：

`<button @click='show(10,$event)'></button>`



### 事件修饰符：

​		`@click.prevent`:阻止默认事件		`@click.stop`:阻止事件冒泡		`@click.once`:时间只触发一次		`@click.capture`:使用捕获事件

​		`@scroll`:滚动条和键盘上下键的滚动事件		`@wheel`:滚动轮滚动事件

​		**事件修饰符可以连着写：如：`@click.stop.prevent`**



## ref

通过ref可以拿到DOM元素

例如一个标签配置`ref=demo`,通过`this.$refs.demo`拿到DOM元素，组件同样适用



## props

可以有两种接收方式：数组方式和对象方式

数组：

```
props:['name','age']
```

对象：

```
props:{		//属性值为接收类型

​	name:String,

​	age:Number

}
```

另一种对象写法：

```
props:{

​	name:{

​		type:String,		//类型

​		required:true/false		//是否是必传的

​	}，
	age:{
		type:NUmber,
		default:100		//如果不传的话的默认值
	}

}
```

props接收的数据不可进行更改

如果props接收参数和data中相同，则会显示props中的数据





若两个组件使用名字相同的class，样式根据后引入哪个组件就使用哪个组件中的样式，若要使用less语法，需要下载依赖less-loader





解绑：**1.**this.$off('事件名')		**2.**this.$off(['事件名1','事件名2'])		**3.**this.$off():解绑所有事件



组件自定义事件：

在子组件标签上绑定一个事件如：`@demo='handleData'`

在子组件中的点击事件中绑定点击事件`@click='handleClick'`

在子组件方法中：handleClick(){

​									this.$emit('**demo**',要传的数据)		//demo就是在子组件中绑定的自定义事件

​							}

在父组件中：

handleData(e){

​		console.log(e)		//e就是传过来的数据

}



在自定义组件标签上写原生事件需要在后面添加`.native`,如:`@click.native`



若一个函数与一个参数没有用到,例如消息发布与订阅中的回调的第一个参数订阅消息名，可以使用下划线占位

`demo(_,data){}`





配置代理服务器：

```
//在vue.config.js中配置代理，若没有vue.config.js文件，需自行创建
devServer: {
	proxy:{
		'/api':{
			target:'http://localhost:5000',	//服务器地址
			pathRewrite:{'^/api':''}
		}
	}
}


//请求时
axios.get('http://localhost:8080/api/...').then()
```





## 打包好的文件放到服务器

首先创建一个服务器server.js

```
const express = require('express');

const app = express();

app.use(express.static(__dirname+'/static'));		

app.get('/person',(req,res) => {
    res.send({
        name:'张磊',
        age:20
    })
})

app.listen('5005',() => {
    console.log('服务器开启成功');
})
```

在目录下新建一个文件夹**static**，把打包后的文件全部放到这个文件夹下，使用`app.use(express.static(__dirname+'/static'));	`来引入文件





**v-model.number**:强制转换为数值类型



vue2中只能用vuex3版本，vue3中只能用vuex4版本

vue2中只能用vue-router3版本，vue3中只能用vue-router4版本



elementui中使用`el-avatar`组件时，使用相对路径加载不出来图片，需要使用`:src="require('相对路径')"`





$route: 一般获取路由信息（路径，query,params等）

$router: 一般进行编程式导航进行路由跳转（push,replace）



**注册完路由，不管路由组件还是非路由组件身上都有$route、$router属性**



面试题：路由传递参数（对象写法），path是否可以和params参数一起使用？

**答：不行。必须使用name给路由命名，并且在对象中使用name才可以和params参数一起使用。**





如何指定params参数可传可不传?

**比如路径为`/home/:id? `,可在params参数占位符id后加`?`**



若是paeams参数为空字符串，则在传递时可写为：`this.$router.push({name:'home',params:{k='' || undefined}})`



路由组件是否可以传递props?

**可以。**

1.布尔值写法：在配置路由中写上`props: true`,即可接收props参数。（只可以接收params参数）。 

2.对象写法： 在配置路由中写上`props: {a: '1', b: '2'}`,即可额外接收props中写入的a,b参数

3.函数写法： 

```
props:($route) => {
	return {keyword: $route.params.keyword, k: $route.query.k}
}
```



编程式导航路由跳转到当前页面（参数不变），多次执行会抛出NavigationDuplicated错误？

路由跳转有两种形式：声明式导航，编程式导航





因为在vue2中直接新增属性、删除属性页面不会更新，

直接通过下标修改数组，页面也不会自动更新

**在vue中给对象添加属性：**

​	**Vue.set(对象，要添加的属性，属性值)  或  this.$set(对象，要添加的属性，属性值)**  



**在vue中给对象删除属性：**

​	**Vue.detele(对象，要添加的属性，属性值)  或  this.$detele(对象，要添加的属性，属性值)**  



**在vue2中修改数组的值**

​		**Vue.set(数组名，下标，值)**
