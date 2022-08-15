#### 发送请求的四种方式：原生，jquery,fetch,axios

 局部刷新需要使用的技术

1) javascript,需要创建XMLHttpRequest对象，调用他的属性或方法

2) 处理DOM，更新select的数据

3) css：处理视图，更新，美化

4) servlet：服务端技术

5) 数据格式：json



把上面这些技术的综合使用叫做Ajax



Ajax=Asynchronous JavaScript and XML(异步的javascript和XML)

Ajax是一种无须加载整个网页的情况下，能够更新部分页面内容的方法

Ajax不是一种新的编程语言，它是多种技术的综合应用，包含了    javascript，dom，css，服务器端技术，json数据格式

 Ajax的核心技术是javascript和XML(JSON)



异步对象XMLHttpRequest的属性和方法

 1.创建对象： var xhr=new XMLHttpRequest();

2.XMLHttpRequest的方法：

  open("请求方式"，"访问的地址"，异步或同步) //异步或同步是布尔值

  send(),使用异步对象发送请求

3.XMLHttpRequest属性：

&nbsp;&nbsp;readyState属性：请求的状态

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0：表示创建异步对象时，new XMLHttpRequest()

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1:表示初始异步对象的请求参数，执行open()

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2:使用send()方法发送请求

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3：使用异步对象从服务器接收了数据

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4：异步对象接收了数据，并在异步对象内部处理完成后

&nbsp;&nbsp;status属性：网络的状态，和Http状态码相对应<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;200：请求成功<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;404：服务器资源没有找到<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;500：服务器内部代码有错误<br> &nbsp;

&nbsp;&nbsp;responseText属性：表示服务器端返回的数据

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：var data=xhr.responseText;



**若想要设置自定义请求头，则需要在服务器中添加`response.setHeader('Access-Control-Allow-Header','*')`,并将服务器中的请求方式改成all方式**



**从服务器返回数据的转换：**

​				**1.手动转换：*<u>JSON.parse(xhr.response)</u>;***

​				**2.自动转换：在函数外设置响应体数据的类型，*<u>xhr.responseType = 'json</u>*'**



<u>安装nodemon，可以在更改服务器代码之后不需要再重启服务</u>



**超时设置2秒：xhr.timeout = 2000;若2秒后没有数据返回，则取消请求**



**手动取消请求：*<u>xhr.abort();</u>***



**取消重复请求：**

```
const btn = document.getElementById('btn');

​    let isSending = false;

​    btn.onclick= function(){

​      const xhr = new XMLHttpRequest();

​      xhr.open('get','http://127.0.0.1:8000/delay');

​      xhr.send();

​      if(isSending) xhr.abort();

​      isSending = true;

​      xhr.onreadystatechange = function(){

​        if(xhr.readyState === 4){

​          isSending = false;

​        }

​      }

​    }
```



**使用jquery发送请求：**

​				**$.get(路径，参数，回调函数,'json')；**

​				**例如：$.get('http://127.0.0.1:8000/serve-jquery',{a:0,b:1},function(data){**

​											**console.log(data);**

​							**},'json')**

​				**若要设置数据为json,只需要在回调函数后面加上'json'**

​			

```
$.ajax({

​				url:'',										//路径

​				data:{},									//参数

​				type:'',									//请求方式

​				dataType:'json'					//相应体为json格式

​				timeout:2000,						//延时2秒

​				headers:{},							//自定义头信息（需要在服务器中添加`response.*setHeader*('Access-Control-Allow-Headers','*');`,并把请求方式改成**all**）

​				success:function(data){	//成功的回调

​						console.log(data)

​				}，

​				error:function(){

​					console.log('出错了');

​				}

​			})
```

​				





​										



