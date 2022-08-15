## let声明作用域

> **let**声明的作用域是块作用域，而**var**声明的范围是函数作用域。

```
//var 声明
if(true){
	var name = "luffy"
	console.log(name)	//"luffy"
}
console.log(name)	//"luffy"


//let声明
if(true){
	var name = "luffy"
	conlose.log(name);	//"luffy"
}
console.log(name);	//ReferecceError:age没有定义
```

