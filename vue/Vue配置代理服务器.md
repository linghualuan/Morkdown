# Vue配置代理服务器

​			在根目录下新建一个vue.config.js文件，配置以下信息：

```js
module.exports = {

        devServer:{

                proxy:{

                        '/api':{

                                target:'http://localhost:8000', //接口的前缀

                                ws:true,	//代理websocked

                                changeOrigin:true,	//虚拟的站点需要更换origin

                                pathRewrite:{

                                            '^/api':''   //重写路径

                                }

                        }

                }

        }

}
```

