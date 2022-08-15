## 1.得到对象的键和值

​		得到键：**Object.keys(对象)**

​		得到值： **Object.values(对象)**

```js
Object.keys()的用法
作用：遍历对象
返回结果：返回对象中每一项key的数组

var obj = {a:'html',b:'css',c:'js'}

var keyValue = Object.keys(obj)

console.log(keyValue)    //['a','b','c']

let arr = {name:'张磊',age:{a:'list1',b:'list2'}}

var keyValue = Object.keys(arr).map(key => arr[key])

console.log(keyValue);  //['张磊',{a:'list1',b:'list2'}]
```



​		**Object.entries(一个键值对为一个数组，多个键值对形成多个数组)**

```js
const school = {
    name: '张磊',
    age: 21,
    subject: ['数据结构','安卓','数据库']
}
console.log(Object.entries(school));
```

![image-20220720143327527](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220720143327527.png)





## 2.使用原型属性减少重复代码

在定义构造函数的时候，若是存在确定属性值的属性，例如

```js
function Dog(name) {
	this.name = name
	this.numLegs = 4
}
```

每次创建新实例的时候都会重复执行`this.numLegs = 4`

最好的办法是numLegs属性在原型上定义：`Dog.prototype.numLegs = 4`

**注意：使用Obj.hasOwnProperty()遍历对象属性时，只能遍历对象自身属性，不可以遍历原型上的属性**





## 3.查看是什么类型的对象

```js
let duck = new Bird();
let beagle = new Dog();

console.log(duck.constructor === Bird);   //true 
console.log(beagle.constructor === Dog);   //true
```



## 4.使用原型添加多个属性

```js
Bird.prototype = {
  numLegs: 2, 
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

副作用：手动将原型设置为新对象有一个重要的副作用。它会删除`constructor`属性！

```js
//实例化对象 ，对象的constructor为false
let newBird = new Bird('zyz')
 console.log(newBird.constructor === Bird);  //false
console.log(duck instanceof Bird)  //true
```

解决办法：

```
Bird.prototype = {
  constructor: Bird,
  numLegs: 2, 
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```





## 5.**了解对象原型的来源**

就像人们从父母那里继承基因一样，一个对象`prototype`直接从创建它的构造函数继承它。使用`isPrototypeOf`方法

```js
function Bird(name) {
  this.name = name;
}

let duck = new Bird("Donald");
Bird.prototype.isPrototypeOf(duck);  //true
```



## 6.继承

```js
function Animal() { }  //定义一个Animal对象
Animal.prototype.eat = function() {		//定义原型上的方法
  console.log("nom nom nom");
};
function Bird() { }		//定义一个Bird对象
Bird.prototype = Object.create(Animal.prototype);  //Bird对象继承Animal的原型
Bird.prototype.constructor = Bird;  //重写constructor

//定义Bird自己的方法
Bird.prototype.fly = function() {
    console.log('fly!!!')
}

//定义一个Bird的实例
let newBird =new Bird();
newBird.fly();		//'fly!!!'
```



## 7.**使用 Mixin 在不相关的对象之间添加通用行为**

行为是通过继承共享的。但是，在某些情况下，继承不是最佳解决方案。

对于不相关的对象，最好使用mixins。mixin 允许其他对象使用函数集合。

```js
let flyMixin = function(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  }
};

let bird = {
  name: "Donald",
  numLegs: 2
};

let plane = {
  model: "777",
  numPassengers: 524
};

flyMixin(bird);
flyMixin(plane);


bird.fly();		//"Flying, wooosh!"
plane.fly();	//"Flying, wooosh!"
```



## 8.**使用闭包保护对象内的属性不被外部修改**

**1.**若是不设置成私有变量，则在函数外部可以随意更改变量的值。代码库的任何部分都可以轻松更改密码和银行账户之类的东西。这可能会导致很多问题。

**2.**将此公共属性设为私有的最简单方法是在构造函数中创建一个变量。这会将变量的范围更改为在构造函数内而不是全局可用。这样，变量只能通过构造函数中的方法访问和更改。

```js
function Bird() {
  let hatchedEgg = 10;

  this.getHatchedEggCount = function() { 
    return hatchedEgg;
  };
}
let ducky = new Bird();
ducky.getHatchedEggCount();
```



## 9.检查对象是否具有某一属性

**对象.hasOwnProperty('属性')   或者   属性  in 对象（name  in person）**





## 10.防止对象属性改变

**Object.freeze(Obj)** 





## 11.获取指定对象所有的自有属性的属性描述符

Object.getOwnPropertyDescriptors(obj):
