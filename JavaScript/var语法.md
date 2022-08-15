## var 声明作用域

> 使用 **var** 在一个函数内部定义一个变量，就意味着变量在函数退出时被销毁。 

```
function test(){
	var msg = "luffy"
}
text()
console.log(msg)	//出错
```

> 在函数内定义变量时省略 **var** 操作符时，可以创建一个全局变量,即可以在函数外部访问到。

```
function test(){
	msg = "luffy"
}
test()
console.log(msg)	//"luffy"
```

## var声明作用域

> 使用 **var** 关键字声明的变量会自动提升到函数作用域的顶部(下面两端代码等价)。

```
function test(){							function test(){								
	coosole.log(age);							var age;
	var age = 20;				<=>            	console.log(age);
}												age = 20;
tets()	//undefined							}
											test();	//undefined
```

