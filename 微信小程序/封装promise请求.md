promise方式请求数据

```
export const request（函数名） = function(parmer){

  return new Promise(function(resolve,reject){

​    wx.request({

​      ...parmer,

​      success:function(result){

​        resolve(result);

​      },

​      fail:function(err){

​        reject(err);

​      }

​    })

  })

}
```

上述代码存放在request文件夹的index.js里

引入：

import {request(函数名)} from "../request(文件夹)/index.js"  

**在微信小程序里一定要把路径写全，其他地方可以不用写index.js**

