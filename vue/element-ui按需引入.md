**首先下载依赖`npm install babel-plugin-component`**



在babel.config.js文件中配置：

```
{
  "presets": [["es2015", { "modules": false }]],
  "plugins": [
    [
      "component",
      {
        "libraryName": "element-ui",
        "styleLibraryName": "theme-chalk"
      }
    ]
  ]
}
```

注意：原文件中有如下结构

```
module.exports = {
  presets: [
    '@vue/cli-plugin-babel/preset'
  ],
}

```

可修改为：

```
module.exports = {
  presets: [
    '@vue/cli-plugin-babel/preset',
    ["@babel/preset-env", { "modules": false }]
  ],
  plugins: [
    [
      "component",
      {
        "libraryName": "element-ui",
        "styleLibraryName": "theme-chalk"
      }
    ]
  ]
}
```

**需要把`["es2015", { "modules": false }]`修改为` ["@babel/preset-env", { "modules": false }]`否则会报错**

引入：

```
import {Button,Select} from 'element-ui'

Vue.component(Button.name, Button);
Vue.component(Select.name, Select);
```

即可使用element-ui组件