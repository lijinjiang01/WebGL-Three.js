# WebGL-Three.js
## 使用工具
编辑器：Sublime Text 3<br>
类库：three.js（版本号：91）
## 第一份Three.js代码（源代码在chapter1中）
### 效果图如下：
![](https://github.com/1123GY/WebGL-Three.js/blob/master/chapter1/web1.gif)
## 第二份Three.js代码（源代码在chapter2中）
### 效果图如下：
![](https://github.com/1123GY/WebGL-Three.js/blob/master/chapter2/web2.gif)
## 第三份Three.js代码（源代码在chapter3中）
### 效果图如下：
![](https://github.com/1123GY/WebGL-Three.js/blob/master/chapter3/web3.gif)
## 基础知识
### Three.js 的三大组件
#### 一.场景：
scene = new THREE.Scene();  /* 新建场景 */<br>
在Three.js中添加的物体都是添加到场景中的。在程序最开始的时候进行实例化，然后将物体添加到场景中即可。
#### 二.照相机：
使用的坐标系是右手坐标系<br>
Three.js提供的照相机分为两种：<br>
##### 正交投影照相机：OrthographicCamera( left, right, top, bottom, near, far )
left — 该属性是可视范围的左平面。你可以将它当做是可渲染部分的左侧边界。<br>
right — 跟left属性一样，不过这次是边界的另外一侧。比这个右侧边界更远的对象不会被渲染<br>
top （上边界）— 可被渲染空间的最上面<br>
bottom （下边界）— 可被渲染空间的最下面<br>
near （近面）— 基于相机所在的位置，从这一点开始渲染场景<br>
far （远面）— 基于相机所在的位置，一直渲染到场景中的这一点 <br>
这六个投影面围成的区域就是相机投影的可见区域。 <br>
三维空间内，只有在这个区域内的物体才会被相机看到。<br>
##### 透视投影照相机：PerspectiveCamera(fov, aspect, near, far)
fov - 可视角度 <br><br>
aspect - 为width/height,通常设置为canvas元素的高宽比。<br>
near- 近端距离 <br>
far- 远端距离 <br>
只有离相机的距离大于near值，小于far值，且在相机的可视角度之内，才能被相机投影到。<br>
#### 三.渲染器
/*创建渲染器*/<br>
renderer=new THREE.WebGLRenderer({      <br>
antialias:true,//antialias:true/false是否开启反锯齿<br>
precision:"highp",//precision:highp/mediump/lowp着色精度选择<br>
alpha:true,//alpha:true/false是否可以设置背景色透明 <br>     
premultipliedAlpha:false,//?      <br>
stencil:false,//?    <br>  
preserveDrawingBuffer:true,//preserveDrawingBuffer:true/false是否保存绘图缓冲     <br>
maxLights:1//maxLights:最大灯光数<br>
}); <br>
WebGLRenderer()中有一些参数我们可以设置，以下这些参数来自于官方文档：<br>
  (1)antialias:<br>
　　  值：true/false<br>
　　  含义：是否开启反锯齿，设置为true开启反锯齿。<br>
  (2)precision:<br>
　　  值：highp/mediump/lowp<br>
　　  含义：着色精度选择。<br>
  (3)alpha:<br>
　　  值：true/false<br>
　　  含义：是否可以设置背景色透明。<br>
  (4)premultipliedAlpha:<br>
　　  值：true/false<br>
　　  含义：？<br>
  (5)stencil:<br>
　　  值：true/false<br>
　　  含义：?<br>
  (6)preserveDrawingBuffer:<br>
　　  值：true/false<br>
　　  含义：是否保存绘图缓冲，若设为true，则可以提取canvas绘图的缓冲。<br>
  (7)maxLights:<br>
　　  值：数值int<br>
　　  含义：最大灯光数，我们的场景中最多能够添加多少个灯光。<br>
