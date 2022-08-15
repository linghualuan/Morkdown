> title:标题组件，用来设置标题。

```
title: {
	text: "标题内容"
}
```

> tooltip: 图表的提示框组件。

![image-20220628000639336](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220628000639336.png)

**tooltip中的trigger为触发方式**，**trigger可选：item，axis，none**

![image-20220628000951703](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220628000951703.png)

> legend: 图例组件。

![image-20220628001752388](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220628001752388.png)

> toolbox:工具箱组件，可以另存为图片等功能。

![image-20220628002645022](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220628002645022.png)

>  grid:网格配置 ，控制线形图，柱状图，图表大小。

```
grid: {
	left: ...,
	right: ...,
	bottom: ...,
	top: ...,
	containLabel: false/true
}
```

left,right,bottom,top的数值为距离dom容器的距离。

containLabel为是否显示刻度。

![image-20220628003357395](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220628003357395.png)

> xAxis:配置x轴相关配置。

type: 类型

boundaryGap: false/true      线条是否跟坐标轴有缝隙

data: ['数据1','数据2',...]    x轴显示的内容



> yAxis:配置y轴相关配置。

配置同上



> series: 系列图表配置，他决定着显示哪种类型的图表。