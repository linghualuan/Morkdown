**promise有三个方法`.then` `.catch` `.finally`	三个方法的参数都是一个函数**



**`resolve`函数的作用是，将`Promise`对象的状态从“未完成”变为“成功”（即从 pending 变为 resolved），在异步操作成功时调用，并将异步操作的结果，作为参数传递出去；`reject`函数的作用是，将`Promise`对象的状态从“未完成”变为“失败”（即从 pending 变为 rejected），在异步操作失败时调用，并将异步操作报出的错误，作为参数传递出去。**



```
new Promise((resolve,reject) => {`

​      `resolve(4);`		//同步任务

​    `}).then((msg) => {`		//then中的代码添加待微任务

​      `console.log(msg);`

​    `},(error) => {`

​      `console.log(error);`

​    `})
```

**必须执行完(resolve,reject)=>{}中的resolve()或reject()才能执行then方法**

**同步任务 > 微任务 > 宏任务**
