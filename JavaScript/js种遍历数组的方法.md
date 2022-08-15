## **1.for方法**

​				

```
var arr = [1,2,3,4,5]

​				for(var i = 0;i<arr.length;i++){

​								console.log(i);

​				}
```



## **2.forEach方法**

```
var arr = [1,2,3,4,5];

arr.forEach(item,index,arr){

​				console.log(item)				//1,2,3,4,5(第一个参数代表数组里的每一项)

​				console.log(index)				//0,1,2,3,4(第二个参数代表数组里每一项的下标)

​				conlose.log(arr)				//5[1,2,3,4,5] (第三个参数代表此数组)

}
```



## **3.map方法**

```
var arr = [1,2,3,4,5];

var s = arr.map(item=>{

​	item = item + 1;

​	return item;

})

console.log(arr,s);	//5[1,2,3,4,5]    5[2,3,4,5,6]
```

***<u>map方法返回一个新数组，不会改变原数组，需要返回每一项</u>***



## **4.**filter方法

```
    var arr = [1,2,3,4,5];

​    var s = arr.filter(item=>{

​      return item != 1;

​    })

​    console.log(arr,s); //5[1,2,3,4,5]    4[2,3,4,5]
```

***<u>filter方法返回一个新数组，不会改变原数组</u>***



## **5.some方法**

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



## **6.every方法**

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



## **7.find方法**

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



## **8.findIndex方法**

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

## 注：以上方法除了for循环，其他都有三个参数，跟forEach中的参数的意义相同，可根据需要指定参数

