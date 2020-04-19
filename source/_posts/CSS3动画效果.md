---
title: CSS3动画效果
date: 2017-12-04 00:32:23
tags: html+CSS
---

### **1. 2D变换**
**Transform(变形)**
`rotate()`旋转函数 取值度数    `transform: rotate(30deg);`
`skew()` 倾斜函数 取值度数   `transform: skew(30deg);`
`scale() `缩放函数 取值 正数、负数和小数   
`transform: scaleX(1.2) scaleY(1.2);`
`translate() `位移函数 像素值   ` transform: translateX(100px);`
`transform-origin()` 改变旋转基点   `transform-origin: 100px 100px;`

### **2. 3D变换**
**1.transform-style（preserve-3d） 建立3D空间**
**2.perspective 景深**
**3.perspective- origin 景深基点**
**4.transform 新增函数**

```
rotateX()
rotateY()
rotateZ()
translateZ()
scaleZ()
```

### **3. animation**

**关键帧——keyFrames ,类似于flash**
`animation:运动名称,运动时间,运动形式,动画延时,播放次数,播放前是否重置`
只需指明两个状态，之间的过程由计算机自动计算关键帧的时间单位
数字：0%、25%、100%等
字符：from(0%)、to(100%)
格式
```
@keyframes 动画名称
{
	动画状态
}

```
:代码展示如下

```
div{
    width:200px;
    height:200px;
    background-color: lightblue;
    margin:150px auto;
}
@keyframes domove {
    0%{width:200px;}
    33%{width:300px;}
    66%{width:600px;}
    100%{width:1000px;}
}
div:hover{    
        animation: domove 3s linear forwards;      
}
```

#### **用animate做一个进度条的效果**
- #### html部分
```
<div id="div1">
    <div></div>
</div>
```
- #### css部分
```
#div1{
        width: 1000px;
        height:30px;
        border: #cccccc solid 1px;
        margin: 200px auto;
        border-radius: 15px;
    }
    #div1 div{
        width: 0;
        height:30px;
        background-color: slategray;
        border-radius: 15px;
        animation: domove 4s linear forwards;
    }
    #div1:hover div{
        animation-play-state:paused;
    }
    @keyframes domove {
        0%{width:0;}
        50%{width:800px;}
        100%{width: 1000px;}
    }
```