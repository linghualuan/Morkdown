# vuex：

​			![vuex](https://vuex.vuejs.org/vuex.png)

### 示例：

​			 **1.Vue Components需要执行一个方法，2 + x (x为State中的一个数据)**

​			**2.需要组件先调用一个API:dispatch		执行dispatch('add',2),向Actions发送，此时来到了Actions,Actions为一个对象，其中必定有一个属性为add，属性的值为fcuntion，为一个函数，函数会收到2这个数据**

​			**3.此时执行commit方法，commit('add',2)传到Mutations,Matations也为对象，必定会有add这个属性，属性值为一个函数function**

**,这个函数可以接收两个东西function(state,2),一个是State中的数据，一个是接收到的数据2，则此时function中执行state.x + 2;**

​			**4.Mutate不需要手动调用**

​			**5.注：Backend API 为后端接口，例如：如果想加的数据（上个例子中为2）需要从后端接口调用，则需要走Actions这一步，否则，若是数据存在组件本身，则可直接调用commit走Mutates这一步，若需要业务逻辑，比如：奇数时再加，间隔一定时间再加就需要经过Actions。**

​			**6.Vue Components相当于去餐厅吃饭的客人，Actions相当于服务员，Mutates相当于厨师，State相当于菜**



------



## 创建文件：

> 在src目录下新建store文件夹，文件夹新建文件index.js

​		**在index.js文件中：**

		//引入vue
	    import Vue from 'vue'
		
		//引入插件
		import Vuex  from 'vuex'
		
		//使用插件
		Vue.use(Vuex)
	
		//准备action---用于响应组件中的动作
		const actions = {},
	
		//准备mutation---用于操作数据（state）
		const mutates = {},
	
		//准备state---用于存储数据
		const state = {
			sum:5,
			school:'郑州轻工业大学',
			name:'luffy'
		},
		
		//准备getters--对state中的数据进行加工，类似于计算属性,组件中读取数据($store.getters.bigSum)=>																								{{($store.getters.bigSum}}
		const getters = {
			bigSum(state){   //参数state为state中的数据
				return state.sum * 10
			}
		}
		
		//创建并暴露store
	  	export default new vuex.Store({
	    	actions,mutations,state，getters
	    });


​		

> 在main.js文件中，引入`import store from './store'`,并在vue实例中`store:store`,简写为`store` ,此时便会给vm和每个组件绑定$store

------



## mapState和mapGetters的使用

### mapstate

​			**作用：**借助mapState生成计算属性，从state中读取数据

​			**使用原因：**在页面中若是想使用模板语法展现数据，如：<h2>我叫{{$store.state.name}},我在{{$store.state.school}}学前端</h2>

，频繁使用$store.state太麻烦，可以使用计算属性：`name(){ return this.$store.state.sum  }`以及

`school(){ return this.$store.state.school  }`,则在页面中可以写为`{{name}}`,`{{school}}`

​			**对象方法：**如果要使用mapState,则可写为：**`mapState({name:'name',school:'school'})`**,**注意：属性值必须要加引号,并且不可以写为简写形式mapState({name,school}),此时会被解析为mapState({name:name,school:school}),会漏掉引号**，会自动生成计算属性，在computed中写：**`...mapState({name:'name',school:'school'})`**    <u>*(因为mapState的数值为一个对象，配置到computed中需要把每个值解析)*</u>，然后会在computed中自动生成`name(){return this.$store.state.sum}`以及`school`

​			**数组方法：**mapState(['name','school']),生成的结果跟对象方法相同

### mapgetters

​			**作用：**借助mapGetters生成计算属性，从getters中读取数据

​			**对象方法：**若要使用getters中的数据，则需写为mapGetters({bigSum:'mapGetters'})

​			**数组方法：**mapGetters(['bigsum'])



## mapMutations和mapActions的使用

### mapMutations

​				**作用：借用mapMutations生成对应的方法，方法中会调用commit去联系mutations。**

​				**例如：**

```
increment(){

	this.$store.commit('JIA',this.n);

},
decrement(){

	this.$store.commit('JIAN',this.n);

}
```

**则需要在methods中写：...mapMutations({increment:'JIA',decrement:'JIAN'})**  ***(对象写法)***

**注：在页面中写引入的方法是要传入参数，如：<button @click="increment(n)">点击加1</button>  (n为data中的数据)**

***实际上由mapMutations生成的方法是：***

```
increment(value){
	this.$store.commit('JIA',value);	//value为鼠标点击事件
}
```

**若不写入参数，则默认value为鼠标点击事件**



### mapActions

​			**作用：借用mapMutations生成对应的方法，方法中会调用dispatch去联系actions。**

​			**格式与mapMutations格式相同**
