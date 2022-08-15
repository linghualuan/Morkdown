

# 1.遍历数组

### **1).for方法**

​				

```
var arr = [1,2,3,4,5]

​				for(var i = 0;i<arr.length;i++){

​								console.log(i);

​				}
```



### **2).forEach方法**

```
var arr = [1,2,3,4,5];

arr.forEach(item,index,arr){

​				console.log(item)				//1,2,3,4,5(第一个参数代表数组里的每一项)

​				console.log(index)				//0,1,2,3,4(第二个参数代表数组里每一项的下标)

​				conlose.log(arr)				//5[1,2,3,4,5] (第三个参数代表此数组)

}
```



### **3).map方法**

```
var arr = [1,2,3,4,5];

var s = arr.map(item=>{

​	item = item + 1;

​	return item;

})

console.log(arr,s);	//5[1,2,3,4,5]    5[2,3,4,5,6]
```

***<u>map方法返回一个新数组，不会改变原数组，需要返回每一项</u>***



### **4).**filter方法

```
    var arr = [1,2,3,4,5];

​    var s = arr.filter(item=>{

​      return item != 1;

​    })

​    console.log(arr,s); //5[1,2,3,4,5]    4[2,3,4,5]
```

***<u>filter方法返回一个新数组，不会改变原数组</u>***



### **5).some方法**

***<u>作用：返回值为布尔值，寻找数组中符合条件的项，只要找到一项符合条件就会返回true，否则返回false</u>***

```
    var arr = [1,2,3,4,5];

​    var s1 = arr.some(item=>{

​      return item === 1;

​    })

​    console.log(s1);	//true



​    var s2 = arr.some(item=>{

​      return item === 9;

​    })

​    console.log(s2);	//false
```



### **6).every方法**

***<u>作用：测试数组中所有的项是否都符合条件，若都符合则返回true，否则返回false</u>***

```
    var arr1 = [1,2,3,4];

​    var s1 = arr1.every(item=>{

​      return typeof item === 'number';

​    })

​    console.log(s1);	//true



​    var arr2 = [1,'男',false,90];

​    var s2 = arr2.every(item=>{

​      return typeof item === 'number';

​    })

​    console.log(s2);	//false
```



### **7).find方法**

***<u>作用:返回第一个通过测试的元素，若没有符合条件的元素则返回undefinded</u>***

```
var arr1 = [1,true,"luffy",4,5];

​    var s1 = arr1.find(item=>{

​      return typeof item === 'string'

​    })

​    console.log(s1);	//luffy



​    var arr2 = [1,2,3,4,5];

​    var s2 = arr2.find(item=>{

​      return typeof item === 'string'

​    })

​    console.log(s2);	undefinded
```





### **8).findIndex方法**

***<u>作用：作用与find方法相同，不同的是findindex返回的是第一个符合条件的项的下标，若没有符合条件的项，则返回-1</u>***

```
var arr1 = [1,true,"luffy",4,5];

​    var s1 = arr1.findIndex(item=>{

​      return typeof item === 'string'

​    })

​    console.log(s1);	//2



​    var arr2 = [1,2,3,4,5];

​    var s2 = arr2.findIndex(item=>{

​      return typeof item === 'string'

​    })

​    console.log(s2);	//-1
```

**注：以上方法除了for循环，其他都有三个参数，跟forEach中的参数的意义相同，可根据需要指定参数**





# 2.数组常用的函数

### 1).push:在数组末尾添加一个元素

```js
var a = [1,2,3];

var b= a.push(5);

console.log(a);

console.log(b);
```



### 2).unshift:在数组开头增加一个元素

```js
var c =  [1,2,3,4];

var d = c.unshift(7);

console.log(c);

console.log(d);
```



### 3).pop:删除和返回最后一个元素

```js
var e = [1,2,3,4];

var f = e.pop();

console.log(e);

console.log("删除的数据是"+f);
```



### 4).shift:删除并返回首个元素

```js
var g = [1,2,3,4];

console.log("原数组是"+g);

var h = g.shift();

console.log(g);

console.log("删除的元素是"+h);
```



### 5).splice:修改删除元素

**splice(参数1，参数2，参数3)：第一个参数是开始的索引，第二个参数是要删除的个数，第三个参数是要添加的值(可以为多个值),       注：会改变原数组**

```js
var i = [1,2,3,4];

var j = i.splice(1,1,7,[0,9,8],6);  //第一个数字表示从哪个下标开始，第二个数字表示要删除下标后面几位，从第三个往后表示要添加的数据

console.log(i);

console.log(j);
```



### 6).concat:合并两个或多个数组

```js
var k = [1,2,3,4];

var l = [5,6,7];

var m = l.concat(k);

console.log(m);
```



### 7).slice:剪切数组元素

**arr.slice([begin[, end]])：第一个参数是开始的下标，第二个参数是结束的下标的前一位,    注：不会改变原数组**

**begin**

从该索引处开始提取原数组中的元素,如果该参数为负数，则表示从原数组中的倒数第几个元素开始提取， slice(-2) 表示提取原数组中的倒数第二个元素到最后一个元素（包含最后一个元素）。如果省略  begin ，则  slice 从索引 0 开始。

**end**

在该索引处结束提取原数组元素（从0开始）。 slice 会提取原数组中索引从  begin 到  end 的所有元素（包含begin，但不包含end）。

slice(1,4) 提取原数组中的第二个元素开始直到第四个元素的所有元素 （索引为 1, 2, 3的元素）。

如果该参数为负数， 则它表示在原数组中的倒数第几个元素结束抽取。 slice(-2,-1) 表示抽取了原数组中的倒数第二个元素到最后一个元素（不包含最后一个元素，也就是只有倒数第二个元素）。

如果 end 被省略，则 slice 会一直提取到原数组末尾。如果  end 大于数组长度， slice 也会一直提取到原数组末尾。

```js

var n = [1,2,3,4];

var o =n.slice(0,1);

// console.log(n===o);

console.log(o);
```



### 8).join:将数组转化为字符串

```js
var p = [1,2,3,4];

var q = p.join(",")

console.log(q);
```



### 9)split:将一个String对象分割成子字符串数组

```js
//split： split() 方法使用指定的分隔符字符串将一个String对象分割成子字符串数组，以一个指定的分割字串来决定每个拆分的位置。

var myString = "Hello World. How are you doing?";

var splits = myString.split(" ", 3); //["Hello", "World.", "How"]
```



### 10).reverse:将数组中元素的位置颠倒

```js
//reverse: reverse() 方法将数组中元素的位置颠倒，并返回该数组。数组的第一个元素会变成最后一个，数组的最后一个元素变成第一个。该方法会改变原数组。

const a = [1, 7, 3];

a.reverse();// [3, 7, 1]
```



### 11).replace:替换指定的内容

```js
const arr = ['name=zl','age=20']

const arrNew = []

arr.forEach(item => {

	arrNew.push(item.replace('=',':'))
	
})

console.log(arrNew)		//['name:zl','age:20']
```

**改变原数组：**sort函数

**不改变原数组：**filter



### 12.计算数组中最大的一个数

**Math.Max(...arr)   //arr为数组**



### 13.判断数组里是否包含某一元素

```js
const demo = ['html','css','js']
console.log(demo.includes('css'))	//true
console.log(demo.includes('vue'))	//false
```

