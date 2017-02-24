# Questions

## CSS面试题

### 1. 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？







### 2. CSS清除浮动的几种方法（至少两种）





### 3. CSS隐藏元素的几种方法（至少说出三种）






### 4. CSS 居中(包括水平居中和垂直居中)





### 5. 介绍一下CSS的盒子模型？




### 6. CSS3有哪些新特性？





## JavaScript面试题

### 1. javascript的typeof返回哪些数据类型



### 2. call和apply的区别




### 3. 闭包是什么，有什么特性，对页面有什么影响?简要介绍你理解的闭包






### 6. 怎样添加、移除、移动、复制、创建和查找节点？









### 7. 如何消除一个数组里面重复的元素？









### 8. 在Javascript中什么是伪数组？如何将伪数组转化为标准数组？










### 9. javascript面向对象中继承实现





### 10. 请描述一下cookies，sessionStorage和localStorage的区别







### 11. 跨域请求资源的方法有哪些？




### 12. 如何阻止事件冒泡和默认事件




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
```

### 14. 谈谈This对象的理解。






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

```

### 16. 对MVC、MVVM的理解






## 附加题


### 1. 一次完整的HTTP事务是怎样的一个过程？








### 2. 你有哪些性能优化的方法？








### 3. 说说最近最流行的一些东西吧？常去哪些网站？







