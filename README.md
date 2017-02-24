# Front-end-Interview-Questions

[TOC]

## CSS面试题

### 1. 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

行内元素：a、b、span、img、input、strong、select、label、em、button、textarea
块级元素：div、ul、li、dl、dt、dd、p、h1-h6、blockquote
空元素：即系没有内容的HTML元素，例如：br、meta、hr、link、input、img

### 2. CSS清除浮动的几种方法（至少两种）

- 使用带clear属性的空元素
- 使用CSS的overflow属性；
- 使用CSS的:after伪元素；
- 使用邻接元素处理；

### 3. CSS隐藏元素的几种方法（至少说出三种）

- Opacity: 元素本身依然占据它自己的位置并对网页的布局起作用。它也将响应用户交互;
- Visibility: 与 opacity 唯一不同的是它不会响应任何用户交互。此外，元素在读屏软件中也会被隐藏;
- Display: display 设为 none 任何对该元素直接打用户交互操作都不可能生效。此外，读屏软件也不会读到元素的内容。这种方式产生的效果就像元素完全不存在;
- Position: 不会影响布局，能让元素保持可以操作;
- Clip-path: clip-path 属性还没有在 IE 或者 Edge 下被完全支持。如果要在你的 clip-path 中使用外部的 SVG 文件，浏览器支持度还要低;

### 4. CSS 居中(包括水平居中和垂直居中)


#### 4.1 内联元素居中方案

##### 4.1.1 水平居中设置
  1. 行内元素

##### 4.1.2 垂直居中

#### 4.2 块级元素居中


### 5. 介绍一下CSS的盒子模型？

- 有两种， IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 padding;
- 盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).

### 6. CSS3有哪些新特性？

- CSS3实现圆角（border-radius:8px），阴影（box-shadow:10px），
对文字加特效（text-shadow、），线性渐变（gradient），旋转（transform）

- transform:rotate(9deg) scale(0.85,0.90) translate(0px,-30px) skew(-9deg,0deg);//旋转,缩放,定位,倾斜
增加了更多的CSS选择器 多背景 rgba


## JavaScript面试题

### 1. javascript的typeof返回哪些数据类型


Ｏbject 、number 、function、 boolean、 underfind;


### 2. 数组方法pop() push() unshift() shift()

- Push()尾部添加 pop()尾部删除

- Unshift()头部添加 shift()头部删除

### 3. ajax请求的时候get 和post方式的区别

- 一个在url后面 一个放在虚拟载体里面
有大小限制
- 安全问题
应用不同 一个是论坛等只需要请求的，一个是类似修改密码的;

### 4. call和apply的区别

- Object.call(this,obj1,obj2,obj3)
- Object.apply(this,arguments)

### 5. 闭包是什么，有什么特性，对页面有什么影响?简要介绍你理解的闭包

闭包就是能够读取其他函数内部变量的函数。

### 6. 怎样添加、移除、移动、复制、创建和查找节点？

1）创建新节点
createDocumentFragment() //创建一个DOM片段
createElement() //创建一个具体的元素
createTextNode() //创建一个文本节点
2）添加、移除、替换、插入
appendChild() //添加
removeChild() //移除
replaceChild() //替换
insertBefore() //插入
3）查找
getElementsByTagName() //通过标签名称
getElementsByName() //通过元素的Name属性的值
getElementById() //通过元素Id，唯一性

### 7. 如何消除一个数组里面重复的元素？

```javascript
// 方法一：
var arr1 =[1,2,2,2,3,3,3,4,5,6],
    arr2 = [];
for(var i = 0,len = arr1.length; i< len; i++){
    if(arr2.indexOf(arr1[i]) < 0){
        arr2.push(arr1[i]);
    }
}
document.write(arr2); // 1,2,3,4,5,6
```

### 8. 在Javascript中什么是伪数组？如何将伪数组转化为标准数组？

伪数组（类数组）：无法直接调用数组方法或期望length属性有什么特殊的行为，但仍可以对真正数组遍历方法来遍历它们。典型的是函数的argument参数，还有像调用getElementsByTagName,document.childNodes之类的,它们都返回NodeList对象都属于伪数组。可以使用Array.prototype.slice.call(fakeArray)将数组转化为真正的Array对象。

```javascript
function log(){
      var args = Array.prototype.slice.call(arguments);  
//为了使用unshift数组方法，将argument转化为真正的数组
      args.unshift('(app)');

      console.log.apply(console, args);
};
```

### 9. javascript面向对象中继承实现

javascript面向对象中的继承实现一般都使用到了构造函数和Prototype原型链，简单的代码如下：

```javascript
function Animal(name) {
   this.name = name;
}
 
Animal.prototype.getName = function() {alert(this.name)}
function Dog() {};
Dog.prototype = new Animal("Buddy");
Dog.prototype.constructor = Dog;
var dog = new Dog();
```

### 10. 请描述一下cookies，sessionStorage和localStorage的区别

sessionStorage用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束后数据也随之销毁。因此sessionStorage不是一种持久化的本地存储，仅仅是会话级别的存储。而localStorage用于持久化的本地存储，除非主动删除数据，否则数据是永远不会过期的。
web storage和cookie的区别
Web Storage的概念和cookie相似，区别是它是为了更大容量存储设计的。Cookie的大小是受限的，并且每次你请求一个新的页面的时候Cookie都会被发送过去，这样无形中浪费了带宽，另外cookie还需要指定作用域，不可以跨域调用。
除此之外，Web Storage拥有setItem,getItem,removeItem,clear等方法，不像cookie需要前端开发者自己封装setCookie，getCookie。但是Cookie也是不可以或缺的：Cookie的作用是与服务器进行交互，作为HTTP规范的一部分而存在 ，而Web Storage仅仅是为了在本地“存储”数据而生。

### 11. 跨域请求资源的方法有哪些？

### 12. 如何阻止事件冒泡和默认事件

```javascript
function stopBubble(e)
{
    if (e && e.stopPropagation)
        e.stopPropagation()
    else
        window.event.cancelBubble=true
}
return false
```

### 13. 下面程序执行后弹出什么样的结果?

```javascript
function fn() {
    this.a = 0;
    this.b = function() {
        alert(this.a)
    }
}
fn.prototype = {
    b: function() {
        this.a = 20;
        alert(this.a);
    },
    c: function() {
        this.a = 30;
        alert(this.a);
    }
}
var myfn = new fn();
myfn.b();
myfn.c();

// 结果
// 0
// 30
```

### 14. 谈谈This对象的理解。

this是js的一个关键字，随着函数使用场合不同，this的值会发生变化。
但是有一个总原则，那就是this指的是调用函数的那个对象。
this一般情况下：是全局对象Global。 作为方法调用，那么this就是指这个对象


### 15. 下面程序的输出结果

```javascript

var name = 'World!';
(function () {
    if (typeof name === 'undefined') {
        var name = 'Jack';
        console.log('Goodbye ' + name);
    } else {
        console.log('Hello ' + name);
    }
})();

// 结果
// Goodbye Jack
```

## HTTP 面试题

### 一次完整的HTTP事务是怎样的一个过程？

基本流程：
a. 域名解析
b. 发起TCP的3次握手
c. 建立TCP连接后发起http请求
d. 服务器端响应http请求，浏览器得到html代码
e. 浏览器解析html代码，并请求html代码中的资源
f. 浏览器对页面进行渲染呈现给用户

## 设计模式

对MVC、MVVM的理解

## 其他

### 1. 你有哪些性能优化的方法？

（1） 减少http请求次数：CSS Sprites, JS、CSS源码压缩、图片大小控制合适；网页Gzip，CDN托管，data缓存 ，图片服务器。

（2）前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数

（3） 用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能。

（4） 当需要设置的样式很多时设置className而不是直接操作style。

（5） 少用全局变量、缓存DOM节点查找的结果。减少IO读取操作。

（6） 避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)。

（7） 图片预加载，将样式表放在顶部，将脚本放在底部 加上时间戳。

（8） 避免在页面的主体布局中使用table，table要等其中的内容完全下载之后才会显示出来，显示div+css布局慢。对普通的网站有一个统一的思路，就是尽量向前端优化、减少数据库操作、减少磁盘IO。向前端优化指的是，在不影响功能和体验的情况下，能在浏览器执行的不要在服务端执行，能在缓存服务器上直接返回的不要到应用服务器，程序能直接取得的结果不要到外部取得，本机内能取得的数据不要到远程取，内存能取到的不要到磁盘取，缓存中有的不要去数据库查询。减少数据库操作指减少更新次数、缓存结果减少查询次数、将数据库执行的操作尽可能的让你的程序完成（例如join查询），减少磁盘IO指尽量不使用文件系统作为缓存、减少读写文件次数等。程序优化永远要优化慢的部分，换语言是无法“优化”的。

### 2. 说说最近最流行的一些东西吧？常去哪些网站？

Node.js、MVVM、React-native,Angular,Weex等
CSDN,Segmentfault,博客园,掘金,Stackoverflow,伯乐在线等


## 参考文档

1. http://web.jobbole.com/88041/
2. http://www.cnblogs.com/bigboyLin/p/5272902.html
