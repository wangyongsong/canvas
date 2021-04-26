# Canvas
 
## 项目展示<a href="https://bigbangbangbangk.github.io/canvas/index.html" style="font-size=30px"> 旋转太极图-时钟-贪吃蛇</a>
  
  1. HTML5`<canvas>`标签用于绘制图像
  2. `<canvas>`元素本身并没有绘制能力（它仅仅是图形的容器） - 您必须使用脚本js来完成实际的绘图任务。  

## 1 使用方法

```html
    <!-- html -->

    <canvas id="canvas" width="600" height="600"></canvas>

```

```javascript

    var canvas = document.querySelector('#canvas');

    //getContext("2d") 对象是内置的 HTML5 对象，拥有多种绘制路径、矩形、圆形、字符以及添加图像的方法。 
    var context = canvas.context('2d');

```

### 1.1 理解

> 1. canvas 画板
> 2. context上下文对象 ---可以理解为画笔
> 3. 3D的是WebGL --有兴趣的可以去了解下

#### 1.1.1 Canvas、 SVG 和 WebGl三者之间的区别

- Canvas 位图，是需要自己画点的白板;  

- SVG 矢量图，是给数据就可以绘制点、线、图形的，基于 XML 的标记语言;  

- WebGL 3D位图，是基于 Canvas 的 3D 框架。

## 2 属性

### 2.1 填充

```javascript

    context.fill()

```

### 2.2 边框

```javascript

    context.stroke()

```

### 2.3 样式

```javascript

    context.fillStyle //填充样式

    context.strokeStyle //边框样式

    context.lineWidth //边框线样式
```

### 2.4 矩形

```javascript

    context.strokeRect( x , y , width , height );//矩形边框

    context.fillRect( x , y , width , height );//矩形填充

```

### 2.5 清除画布

```javascript

    // x,y 起始点
    // width,height 清除的宽高
    context.clearRect(x, y, width, height);


    context.clearRect( 0 , 0 , canvas.width , canvas.height );


```

### 2.6 圆弧

```javascript

    // x,y 圆心
    // radius 半径
    // startAngle 起始角  （Math.PI / 180 * startAngle）--弧度
    // endAngle 结束角    （Math.PI / 180 * endAngle）--弧度
    // anticlockwise      true 逆时针  false 顺时针
    context.arc(x, y, radius, Math.PI / 180 * startAngle, Math.PI / 180 * endAngle, anticlockwise);


```

### 2.7 路径

```javascript

    //解决连接线的问题

    context.beginPath()//开始路径
    
    context.closePath()//结束路径

```

### 2.8 线段

```javascript

    context.moveTo(x,y);

    context.lineTo(x,y);


```

### 2.9 文本绘制

```javascript

    context.fillText('文本',x,y);

    context.strokeText('文本',x,y);


```

### 2.10 渐变

```javascript

    //线性渐变
    context.createLinearGradient(x1, y1, x2, y2);

    //放射状/环形的渐变
    context.createRadialGradient(x1, y1, r1, x2, y2, r2);

```

### 2.11 绘制图像、画布或视频

```javascript

    context.drawImage(Image, dX, dY, dWidth, dHeight);


```

### 2.12 转换

```javascript
    //位移
    context.translate(x, y);

    //旋转
    context.rotate(Math.PI / 180 * degree);

    //缩放
    context.scale(x, y);

    //替换绘图的当前转换矩阵
    context.transform(a, b, c, d, e, f);

    //将当前转换重置为单位矩阵。然后运行 transform() 
    context.setTransform(a, b, c, d, e, f) 
    // a 水平旋转绘图
    // b 水平倾斜绘图
    // c 垂直倾斜绘图
    // d 垂直缩放绘图
    // e 水平移动绘图
    // f 垂直移动绘图

```

### 2.13 保存

```javascript

    context.save();//保存当前环境的状态

```

### 2.14 恢复

```javascript

    context.restore();//返回之前保存过的路径状态和属性


```
