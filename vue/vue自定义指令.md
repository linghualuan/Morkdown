## **自定义指令：**

​	**两种形式：函数形式和对象形式**

##				全局自定义指令:

```
						Vue.directives('big',{

​								bind(el,binding){			//bind为自定义指令中的钩子函数

​											console.log();	

​								}

​						})
```

### 			局部自定义指令：

```
						`directives:{`

​								`//函数形式`

​								`big(el,binding){`

​										`console.log();`

​								`}`

​								`//对象形式`

​								`big:{`

​										`bind(el,binding){`

​												`console.log();`

​										`}`

​								`}`

​						`}
```

​				

​				**注：若给自定义指令命名时名字中有横线，则需写成:**

```
								'big-number'(el,binding){

​										console.log();

​								}
```

​			***所有指令中的this都是window***

​			**binding指自定义指令中的内容,如：v-big='xxx' , binding.value即为xxx**

​			**自定义指令中的  函数写法  相当于对象写法中  bind  和  update  相结合**

