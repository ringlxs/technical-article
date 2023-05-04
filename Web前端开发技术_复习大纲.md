[toc]

**基础部分可参照：**

w3school官网：https://www.w3school.com.cn/

菜鸟教程：https://www.runoob.com/



**Vue部分参照官网：**

https://cn.vuejs.org/v2/guide/



# JavaScript

## 常用对象

## 字符串String

相关方法：`charAt()`，`slice()`，`indexOf()`，`lastIndexOf`等等。

##### (1)`charAt()`

###### 实例:

返回字符串中的第三个字符:

```javascript
var str = "HELLO WORLD";
 var n = str.charAt(2)
```

 *n*输出结果:

> L

定义和用法:

- charAt() 方法可返回指定位置的字符。
- 第一个字符位置为 0, 第二个字符位置为 1,以此类推.

##### (2)**`slice()`**

###### 实例

提取字符串的片断:

```javascript
var str="Hello world!";
 var n=str.slice(1,5);
```

 *n* 输出结果：

> ello

##### (3)**`indexOf()`**

###### 实例

查找字符串 "welcome":

```javascript
var str="Hello world,welcome to the universe.";
 var n=str.indexOf("welcome");
```

*n* 输出结果:

> 13

###### 定义和用法

- indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置（空格也算）。
- 如果没有找到匹配的字符串则返回 -1。

- **注意：** indexOf() 方法区分大小写。

##### (4)lastIndexOf()

###### 实例

查找字符串 "runoob" 最后出现的位置:

```javascript
var str="I am from runoob，welcome to runoob site."; 
var n=str.lastIndexOf("runoob");
```

  *n* 输出结果:

> 28

###### 定义和用法

- lastIndexOf() 方法可返回一个指定的字符串值最后出现的位置，如果指定第二个参数 start，则在一个字符串中的指定位置从后向前搜索。
- **注意：** 该方法将从后向前检索字符串，但返回是从起始位置 (0) 开始计算子字符串最后出现的位置。 看它是否含有字符串。
- 开始检索的位置在字符串的 start 处或字符串的结尾（没有指定 start 时）。
- 如果没有找到匹配字符串则返回  -1 。
- **注意：**lastIndexOf() 方法是区分大小写的！



### 数组Array

常用方法：

- 自身发生改变：`push()`，`pop()`，`unshift()`，`shift()`，`reverse()`，`splice()`，`sort()`
- 自身不变，取返回值：`slice()`,`indexOf()`，`lastIndexOf()`等。

##### (1)push()

###### 实例

数组中添加新元素：

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 fruits.push("Kiwi")
```

*fruits* 结果输出：

> Banana,Orange,Apple,Mango,Kiwi

###### 定义和用法

- push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度。
- **注意：** 新元素将添加在数组的末尾。
- **注意：** 此方法改变数组的长度。

##### (2)`pop()`

###### 实例

移除最后一个数组元素：

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();
```

*fruits* 结果输出：

> Banana,Orange,Apple

###### 定义和用法

- pop() 方法用于删除数组的最后一个元素并返回删除的元素。
- **注意：**此方法改变数组的长度！
- **提示：** 移除数组第一个元素，请使用 [shift()](https://www.runoob.com/jsref/jsref-shift.html) 方法。

##### (3)`unshift()`

###### 实例

将新项添加到数组起始位置:

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 fruits.unshift("Lemon","Pineapple");
```

 *fruits* 将输出：

> Lemon,Pineapple,Banana,Orange,Apple,Mango

##### (4)`shift()`

###### 实例

从数组中移除元素,把数组的第一个元素从其中删除:

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 fruits.shift();
```

 *fruits*结果输出:

> Orange,Apple,Mango

##### (5)`reverse()`

###### 实例

颠倒数组中元素的顺序：

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 fruits.reverse();
```

*fruits* 结果输出：

> Mango,Apple,Orange,Banana

##### (6)`splice()`

###### 实例

移除数组的第三个元素，并在数组第三个位置添加新元素:

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 fruits.splice(2,1,"Lemon","Kiwi");
```

*fruits* 输出结果：

> Banana,Orange,Lemon,Kiwi,Mango

###### 定义和用法

- splice() 方法用于添加或删除数组中的元素。
- **注意：**这种方法会改变原始数组。

##### (7)`sort()`

###### 实例

数组排序：

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 fruits.sort();
```

*fruits* 输出结果：

> Apple,Banana,Mango,Orange

###### 定义和用法

- sort() 方法用于对数组的元素进行排序。
- 排序顺序可以是字母或数字，并按升序或降序。
- 默认排序顺序为按字母升序。
- **注意：**当数字是按字母顺序排列时"40"将排在"5"前面。
- 使用数字排序，你必须通过一个函数作为参数来调用。
- 函数指定数字是按照升序还是降序排列。

数字排序（数字和升序）：小于0，升序

```javascript
var points = [40,100,1,5,25,10];
 points.sort(function(a,b){return a-b});
```

fruits输出结果：

> 1,5,10,25,40,100

数字排序（数字和降序）：大于0，降序

```javascript
var points = [40,100,1,5,25,10];
 points.sort(function(a,b){return b-a});
```

fruits输出结果：

> 100,40,25,10,5,1

数字排序 (字母和降序):

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
 fruits.sort();
 fruits.reverse();
```

fruits输出结果：

> Orange,Mango,Banana,Apple

##### (8)`slice()`

###### 实例

在数组中读取元素：

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"]; 
var citrus = fruits.slice(1,3);
```

*citrus* 结果输出:

> Orange,Lemon

###### 定义和用法

- slice() 方法可从已有的数组中返回选定的元素。
- slice()方法可提取字符串的某个部分，并以新的字符串返回被提取的部分。
- **注意：** slice() 方法不会改变原始数组。



### 日期Date

相关方法：

获取年，月，日，时，分，秒，日期，星期，毫秒，距离`1970年1月1日的毫秒数`。

```javascript
<body>
    <div >
        <strong>现在的时间点为:</strong>
        <button onclick="myDate()">当前时间</button>
        <span id="date" ></span>
    </div>
    <div>
        <strong>距离1970年1月1日的毫秒数:</strong>
        <button onclick="myDate1()">毫秒数</button>
        <span id="date1" ></span>
    </div>
    <script>
        function myDate(){
            var date=new Date();//建一个日期对象
            var year=date.getFullYear();//年
            var month=date.getMonth()+1;//月，得加1
            var day=date.getDate();//日
            var hours=date.getHours();//小时
            var minutes=date.getMinutes();//分钟
            var seconds=date.getSeconds();//秒
            month=checkTime(month);
            day=checkTime(day);
            hours=checkTime(hours);
            minutes=checkTime(minutes);
            seconds=checkTime(seconds);
            document.getElementById("date").innerHTML=year+"年"+month+"月"+day+"日"+hours+":"+minutes+":"+seconds;
            setTimeout(function(){myDate()},1000);//每一秒自动刷新一次
        }
        function checkTime(i){
            if(i<10){
                i="0"+i;
            }
            return i;
        }
    </script>
    <script>
        function myDate1(){
            var d = new Date();
            var x = document.getElementById("date1");
            x.innerHTML=d.getTime();
        }
    </script>
</body>
```

![image-20210525212444215](C:\Users\20837\AppData\Roaming\Typora\typora-user-images\image-20210525212444215.png)

## 函数


- 普通函数`function fn() {}`
- 构造函数`new Object()`，大写字母开头的函数，如：`Object`，`Date`
- 返回值，`return`关键字，1.指定返回值，2.结束函数调用
- 系统函数

  - `parseInt()`，`parseFloat()`等
  - 定时器：`setTimeout`，`setInterval`

##### （1）parseInt

> parseInt ("字符串")
> 将字符串转换为整型数字 
> 如: parseInt ("86")将字符串“86“转换为整型值86

##### （2）parseFloat

> parseFloat("字符串")
> 将字符串转换为浮点型数字 
> 如: parseFloat("34.45")将字符串“34.45“转换为浮点值34.45

##### (3)setTimeout()

setTimeout() 是属于 window 的方法，该方法用于在指定的毫秒数后调用函数或计算表达式。

语法格式可以是以下两种：

```javascript
setTimeout(要执行的代码, 等待的毫秒数)
setTimeout(JavaScript 函数, 等待的毫秒数)
//反正的有一个逗号规定毫秒数
语法详情：setTimeout("调用的函数",等待的毫秒数)
```

###### 实例

```javascript
<p id="content"> 请等三秒钟!</p>   
<script>   
    setTimeout("changeState()",3000 );  
    function changeState(){       
    	let content=document.getElementById('content');      
    	content.innerHTML="<div style='color:red'>我是三秒后显示的内容！</div>";   
    }   
</script>
```



##### (4)`setInterval`

```javascript
语法：setInterval("调用的函数",间隔的毫秒数)
```



###### 实例

每三秒（3000 毫秒）弹出 "Hello" :

```javascript
setInterval(function(){ alert("Hello"); }, 3000);
```

- setInterval() 方法会不停地调用函数，直到 [clearInterval()](https://www.runoob.com/jsref/met-win-clearinterval.html) 被调用或窗口被关闭

##### (5)setInterval()与setTimeout特点及区别

特点
         setInterval()和setTimeout()用来处理延时和定时任务
区别
         setTimeout() 方法用于在指定的毫秒数后调用函数或计算表达式，而setInterval()则可以在每隔指定的毫秒数循环调用函数或表达式

## 事件

event 事件对象是事件相关的一系列信息的集合

事件流的执行机制：**捕获，执行，冒泡**

主要使用鼠标事件对象`MouseEvent`和键盘事件对象`KeyboardEvent`

>  在标签中使用事件，以`on+事件名`为标识



### 事件分类

鼠标事件对象：`MouseEvent`

- click，鼠标完成一次左键点击
- mouseover，鼠标移入元素
- mouseout，鼠标移出元素
- mouseenter，鼠标指针进入元素范围
- mouseleave，鼠标指针离开元素
- mousemove，鼠标指针在元素中移动
- mousedown，鼠标左键按下
- mouseup，鼠标左键松开



键盘事件对象：`KeyboardEvent`

- keydown，键盘键被按下
- keypress，键盘键值生效
- keyup，键盘键松开



表单

- focus，聚集
- blur，失去焦点
- change，值改变
- submit，表单提交
- reset，表单重置

[ jQuery 事件方法](https://www.runoob.com/jquery/jquery-ref-events.html)

##### （1）jQuery submit() 方法

###### 实例

当提交表单时，显示警告框：

​    

```javascript
  $("form").submit(function(){
  alert("提交");
	});  
```

------

###### 定义和用法

- 当提交表单时，会发生 submit 事件。
- 该事件只适用于 <form> 元素。
- submit() 方法触发 submit 事件，或规定当发生 submit 事件时运行的函数。





UI事件：

- onload（加载完后触发）加载完毕
  
  - 与`document.DOMContentLoaded`（立即触发）区别
  
  当纯HTML被完全加载以及解析时，**`DOMContentLoaded`** 事件会被触发，而无需等待样式表，图片或者子框架完成加载。
  
  **`load`**当整个页面加载时触发该事件，包括所有依赖资源，如样式表和图像。这与 相比[`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event)，**`DOMContentLoaded`**它在页面 DOM 加载后立即触发，无需等待资源完成加载。
  
- resize窗口大小变化

  指定一个div元素，允许用户调整大小。



语法：

```js
// 添加事件
DOM元素.addEventListener(事件名，函数);

// 移除事件
DOM.removEventListener(事件名，函数)

// 标签内直接添加 on事件名="函数()"
```



## DOM操作

**增**：先创建DOM元素，再添加到页面中

1. 创建`document.creatElement(标签名);`
2. `元素.appenChild(新DOM元素)；`添加



**删**：从文档中移除DOM元素，2种方式效果相同
`元素.remove();`直接删除自己
`子元素.parentElement().removeChild(子元素);`先获取父元素，然后删除自己



**改**：修改DOM元素属性

设置DOM元素属性及属性值：`元素.seAttribute(属性名, 属性值)`



**查**：从文档页面中获取DOM元素的方法
`document.geElementById()`



## BOM操作

location：负责地址栏相关操作

- `location.href = '新地址'`，页面
- `locaction.reload()`，页面刷新



history：负责浏览器的浏览历史

- `history.forward()`，前进
- `history.back()`，后退
- `history.go(数字)`，按照数字步进

<img src="C:\Users\20837\AppData\Roaming\Typora\typora-user-images\image-20210727210621875.png" alt="image-20210727210621875" style="zoom:80%;" />

# CSS

## 引入方式

内部样式，外部样式，行内样式

##### (1)内部样式

```javascript
<head> 
    <style> 
        hr {color:sienna;} 
        p {margin-left:20px;} 
        body {background-image:url("images/back40.gif");} 
    </style> 
</head>
```




##### (2)外部样式

```
<head>
    <link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```




##### (3)行内样式

```
<p style="color:sienna;margin-left:20px">这是一个段落。</p>
```



## 常用设置

- 字体
- 文本
- 背景
- 盒子模型
- 定位与层级
- 2D特效：过渡，动画
- 伪类
  - 鼠标悬浮
  - 超链接伪类：已访问，未访问，鼠标按下未释放

##### (1)字体

字型：

```html
p{font-family:"Times New Roman", Times, serif;}
```

大小：

```
p {font-size:14px;}
```

样式： 

```
 p.normal {font-style:normal;}//正常
 p.italic {font-style:italic;}//斜体
 p.oblique {font-style:oblique;}//倾斜的文字
```

##### (2)文本

颜色：

```
body {color:red;} h1 {color:#00ff00;} h2 {color:rgb(255,0,0);}
```

对齐方式：

```
h1 {text-align:center;} p.date {text-align:right;} p.main {text-align:justify;}
```

文本修饰：

```css
a {text-decoration:none;}/*删除链接的下划线*/
h1 {text-decoration:overline;}/*文字上方划线*/
h2 {text-decoration:line-through;}/*文字中间划线*/
h3 {text-decoration:underline;}/*下划线*/
```

缩进：

```css
p {text-indent:2em;}/*首行缩进两字符*/
```

##### (3)背景

颜色：

```
body {background-color:#b0c4de;}
```

图像：

```
body {background-image:url('bgdesert.jpg');}
```

定位与不平铺：

```
body
 {
 background-image:url('img_tree.png');
 background-repeat:no-repeat;
 background-position:right top;
 }
```

简写：

```
body {background:#ffffff url('img_tree.png') no-repeat right top;}
```

##### (4)盒子模型

- **Margin(外边距)** - 清除边框外的区域，外边距是透明的。
- **Border(边框)** - 围绕在内边距和内容外的边框。
- **Padding(内边距)** - 清除内容周围的区域，内边距是透明的。

##### (5)定位与层级

static（静态默认）定位：

- HTML 元素的默认值，即没有定位，遵循正常的文档流对象。
- 静态定位的元素不会受到 top, bottom, left, right影响。

fixed（固定）定位：

- 元素的位置相对于浏览器窗口是固定位置，即使窗口是滚动的它也不会移动。

```css
p.pos_fixed {    position:fixed;    top:30px;    right:5px; }
```

relative（相对）定位:

- 相对定位元素的定位是相对其正常位置。

```css
h2.pos_left {    
    position:relative;    
    left:-20px; /*从元素的原始左侧位置减去 20 像素。*/
} 
h2.pos_right {    
    position:relative;   
    left:20px;/*向元素的原始左侧位置增加 20 像素。*/
}
```

absolute（绝对）定位：

```css
h2 {    
    position:absolute;    
    left:100px;    
    top:150px; 
    /*用绝对定位,一个元素可以放在页面上的任何位置。标题下面放置距离左边的页面100 px和距离页面的顶部150 px的元素*/
}
```

sticky (粘贴)定位：

- 元素定位表现为在跨越特定阈值前为相对定位，之后为固定定位。

元素堆叠：

```css
img {    
    position:absolute;    
    left:0px;   
    top:0px;    
    z-index:-1; /*属性值为 -1, 所以它会显示在文字之后*/
}
```

##### (6)伪类

```javascript
li:link {color: rgb(208, 162, 77)}      /* 未访问链接*/
li:visited {color: rgb(208, 162, 77)}  /* 已访问链接 */
li:hover {color: #fff;}  /* 鼠标移动到链接上 */
li:active {color: #fff;}  /* 鼠标点击时 */
```

##### (7)过渡

应用于宽度和高度属性的过渡效果，时长为 2 秒：

```css
<style> 
div
{
	width:100px;
	height:100px;
	background:red;
    //过渡
	transition:width 2s,height 2s;/*这里有的，下面也要有*/
	-webkit-transition:width 2s,height 2s; /* Safari */
    /*
    或者直接写成这样,不需要那么多花里胡哨的东西。
    transition:2s;
    */
}

div:hover
{
	width:300px;
	height:200px;
}
</style>
```

##### (8)动画

动画主要有三个：移动，缩放，旋转。再了解一下透视和3D就阔以了。

具体详见：https://doc.houdunren.com/css

要创建 CSS3 动画，你需要了解 @keyframes 规则。

@keyframes 规则是创建动画。 

@keyframes 规则内指定一个 CSS 样式和动画将逐步从目前的样式更改为新的样式。

```css
<style> 
div
{
	width:100px;
	height:100px;
	background:red;
	animation:myfirst 5s;
	-webkit-animation:myfirst 5s; /* Safari and Chrome */
}

@keyframes myfirst
{
	from {background:red;}
	to {background:yellow;}
}

@-webkit-keyframes myfirst /* Safari and Chrome */
{
	from {background:red;}
	to {background:yellow;}
}
</style>
```

- 当在 **@keyframes** 创建动画，把它绑定到一个选择器，否则动画不会有任何效果。
- 指定至少这两个CSS3的动画属性绑定向一个选择器：
- - 规定动画的名称
  - 规定动画的时长

###### 选择器

### 基本选择器

class选择器，id选择器，标签选择器



### 高级选择器
后代，兄弟，属性，特殊元素
如：`:empty选择器用于选择没有子元素或文本内容为空的所有元素`



# HTML

## 标签

结构标签：`html`，`head`，`title`, `body`

- 标题：h1~h6

- 段落：p

- 图像：img
  - `title`属性：图像标题
  - `alt`属性：图像无法显示的替代文字

- 超链接：a
  
  - `href`属性：链接地址
  
- `target`属性：链接打开方式
  
    
  
  | _blank | 在新窗口中打开被链接文档。           |
  | ------ | ------------------------------------ |
  | _self  | 默认。在相同的框架中打开被链接文档。 |
  
- 列表
  - 无序列表：ul
  - 有序列表：ol
    - 列表项：li
  - 定义列表：dl
    - 分组标题：dt
    - 列表项：dd

- 表格：table
  - 行：tr
  - 单元格：td
    - rowspan跨行，跨列colspan

- 表单：form
  - `<input type="类型" value="默认值"/>`
  
  - 文本框(text)，密码框(password)，单选按钮(radio)，复选框(checkbox)，
  
  - 下拉列表框
  
    ```
    <select name="cars">
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    </select>
    ```
  
    ，提交按钮（submit），
  
    多行文本域（textarea）
  
    ```
    <textarea placeholder="请输入内容" rows="10" cols="30"></textarea>
    ```
  
    
  
  - 高级用法
    - `disabled`，禁用表单元素，
    
    ```
    <button type="button" disabled>点我！</button> 
    ```
    
    - `readonly`，值不可改变

```
      <input type="text"  value="Norway" readonly>
```



# Vue

MVVM渐进式框架，核心思想：数据驱动，组件化。

官网：`https://vuejs.org/`



## 基础

### 指令
v-if,v-else,v-show,v-bind,v-on,v-for....
条件类，显示类，绑定类

<img src="C:\Users\20837\AppData\Roaming\Typora\typora-user-images\image-20210802105952887.png" alt="image-20210802105952887" style="zoom:80%;" />

###### 起步

语法格式如下：

```
var vm = new Vue({
  // 选项
})
```

### 计算属性computed

用于复杂运算，带缓存

##### computed vs methods

我们可以使用 methods 来替代 computed，效果上两个都是一样的，但是 computed 是基于它的依赖缓存，只有相关依赖发生改变时才会重新取值。而使用 methods ，在重新渲染的时候，函数总会重新调用执行。可以说使用 computed 性能会更好，但是如果你不希望缓存，你可以使用 methods 属性。（简单来说就是computed不会重复执行代码，而menthods会重新执行代码）

```
<div id="app">
  <p>原始字符串: {{ message }}</p>
  <p>计算后反转字符串: {{ reversedMessage }}</p>
  <p>计算后反转字符串: {{ reversedMessage }}</p>
  <p>使用方法后反转字符串: {{ reversedMessage2() }}</p>
  <p>使用方法后反转字符串: {{ reversedMessage2() }}</p>
</div>
```



```vue
var cnt=1;
var vm = new Vue({
  el: '#app',
  data: {
    message: 'Runoob!'
  },
  computed: {
    // 计算属性的 getter
    reversedMessage: function () {
      // `this` 指向 vm 实例
      cnt+=1;
      return cnt+this.message.split('').reverse().join('')
    }
  },
  methods: {
    reversedMessage2: function () {
      cnt+=1;
      return cnt+this.message.split('').reverse().join('')
    }
  }
})
```

> 原始字符串: Runoob!
>
> 计算后反转字符串: 2!boonuR
>
> 计算后反转字符串: 2!boonuR
>
> 使用方法后反转字符串: 3!boonuR
>
> 使用方法后反转字符串: 4!boonuR

### 侦听器watch

侦听data数据变化



### 过滤器filter

用于格式化文本





```html
<div id="app">
    <!-- 计算属性，不需要加小括号() -->
    <div>
        总价：{{total}}
    </div>
    <!-- 把second的值传入timerFormater过滤器，处理结果是timerFormater的返回值 -->
    <span>时间：{{ second | timerFormater }}</span>
</div>
<script>
    var vm = new Vue({
		el:'#app',
        data:{
            num: 0,
            second: 8
        },
        // 侦听器
        watch:{
            num(){
                // 侦听num变化操作，num变化，当前函数就会执行，可以不指定返回值
            }
        },
        // 计算属性
        computed:{
            total(){
                // 必须有个运算结果的返回值
                return this.num * 5;
            }
        },
        // 过滤器
        filters:{
            // 数字补0
            timerFormater(val){
                if(val < 10){
                    return '0' + val;
                } else {
                    return val;
                }
            }
        }
    });
</script>
```



## 路由

VueRouter实例，模式，跳转方法

> 案例见课堂代码



## 组件

组件定义，组件传参方式

> 参照官网和课堂代码