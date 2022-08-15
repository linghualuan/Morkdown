## 创建路由器

> 首先下载路由器插件  `npm i vue-router`
>
> 创建两个或以上组件，例如：Home插件和About插件
>
> 在src文件夹下新建一个文件夹`router` ,文件夹下有一个文件`index.js`
>
> 在`index.js`中配置如下：
>
> ​				1.首先引入`vue-router` ,		`import VueRouter from 'vue-router'`
>
> ​				2.再引入两个组件，`import Home from '../components/Home'`	`import About from '../components/About'`
>
> ​				3.创建并暴露一个路由器 
>
> ​					`export default new VueRouter({`
>
> ​						`routes:[`
>
> ​							`{path:'/about',component:About},`
>
> ​							`{path:'/home',component:Home}`
>
> ​						`]`
>
> ​					`})`
>
> 在main.js中先引入vue-router，`import VueRouter from 'vue-router'`
>
> 在main.js中引入`router`, `import router from './router'`(默认为引入router文件夹下的index.js文件)
>
> 使用插件`Vue.use(VueRouter)`
>
> 在Vue实例中配置`router:router`