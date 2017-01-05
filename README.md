# For-Front-end-Engineer
整理了最近被问到的前端面试题目以及答案

![MacDown logo](https://img10.360buyimg.com/wympay/jfs/t3820/58/2200196988/439902/f753f08/58539afbN9c3422c1.png)

# 一、 HTML

### 常见Meta标签以及含义
    
 * 答：META标签分两大部分：HTTP标题信息(HTTP-EQUIV)和页面描述信息(NAME)。
    
        ★HTTP-EQUIV  ： HTTP-EQUIV类似于HTTP的头部协议，它回应给浏览器一些有用的信息，以帮助正确和精确地显示网页内容。常用的HTTP-EQUIV类型有：

　　1、Content-Type和Content-Language (显示字符集的设定)
　　说明：设定页面使用的字符集，用以说明主页制作所使用的文字已经语言，浏览器会根据此来调用相应的字符集显示page内容。

　　2、Refresh (刷新)
　　　说明：让网页多长时间（秒）刷新自己，或在多长时间后让网页自动链接到其它网页。

　　3、Expires (期限)
　　　说明：指定网页在缓存中的过期时间，一旦网页过期，必须到服务器上重新调阅。

　　4、Pragma (cach模式)
　　　说明：禁止浏览器从本地机的缓存中调阅页面内容。

　　5、Set-Cookie (cookie设定)
　　说明：浏览器访问某个页面时会将它存在缓存中，下次再次访问时就可从缓存中读取，以提高速度。当你希望访问者每次都刷新你广告的图标，或每次都刷新你的计数器，就要禁用缓存了。通常HTML文件没有必要禁用缓存，对于ASP等页面，就可以使用禁用缓存，因为每次看到的页面都是在服务器动态生成的，缓存就失去意义。如果网页过期，那么存盘的cookie将被删除。

　　6、Window-target (显示窗口的设定)
　　　说明：强制页面在当前窗口以独立页面显示。


　　7、Pics-label (网页RSAC等级评定)
　　　说明：在IE的Internet选项中有一项内容设置，可以防止浏览一些受限制的网站，而网站的限制级别就是通过该参数来设置的。

　　8、Page-Enter、Page-Exit (进入与退出)
　　　说明：这个是页面被载入和调出时的一些特效。

   9、Content-Script-Type (脚本相关)
　　　说明：这是近来W3C的规范，指明页面中脚本的类型。

    ★NAME变量 ： name是描述网页的，对应于Content（网页内容），以便于搜索引擎机器人查找、分类（目前几乎所有的搜索引擎都使用网上机器人自动查找meta值来给网页分类）：
    
    
   1、Keywords (关键字)
　　　说明：为搜索引擎提供的关键字列表

　　2、Description (简介)
　　　说明：Description用来告诉搜索引擎你的网站主要内容。

　　3、Robots (机器人向导)
　　　说明：Robots用来告诉搜索机器人哪些页面需要索引，哪些页面不需要索引。Content的参数有all、none、index、noindex、follow、nofollow。默认是all。

　　4、Author (作者)
　　　说明：标注网页的作者或制作组

　　5、Copyright (版权)
　　　说明：标注版权

　　6、Generator (编辑器)
　　　说明：编辑器的说明

　　7、revisit-after (重访)。

　　 ★Head中的其它一些用法

　　1、scheme (方案)
　　　说明：scheme can be used when name is used to specify how the value of content should　be interpreted.

　　2、Link (链接)
　　　说明：链接到文件

　　3、Base (基链接)
　　　说明：插入网页基链接属性
    
  原文链接：<http://www.cnblogs.com/esshs/articles/157588.html>
  
  
# 二、css

### （一）、那些css属性会引起浏览器重排？
  
 答：重排是指一种改变，可以理解为渲染树需要重新计算。下面是常见的触发重排的操作：

* 重新调整浏览器窗口大小
* 修改字体
* 添加、删除样式表
* 修改页面元素内容
* 激活CSS伪类，如a:hover
* 修改class的属性
* 修改DOM
* 计算offsetWidth和offsetHeight
* 设置style的属性

如何避免重排或者减少重排带来的性能问题。
    
* 修改元素的class属性，并且尽可能在DOM树中比较低的节点上
* 避免在内联样式中设置多重属性
* 将动画应用在absolute定位或者fixed的元素上
* 减少table布局
* 避免使用CSS表达式

### （二）、Sass和Less

1. Sass的常见语法
 * 答：参考慕课网的课程吧。挺好的 [Sass入门篇](http://www.imooc.com/learn/311) [Sass进阶篇](http://www.imooc.com/learn/436)
    
2. 使用预编译处理有什么好处？（可以使用css完成，为什么使用Sass？）
 * 答：

 
# 三、JavaScript
### （一）、基础知识之原型链
```
function P(){}

var p = new P();

p.prototype.constructor 指向？：指向函数本身，即 p 。

p.constructor 指？ ： 指向它的构造函数，即 P 。

p.[[proto]] 指？ ： 指向它的构造函数的原型，即 P.prototype 。
```
参考课程 [zepto设计和源码分析](http://www.imooc.com/learn/745)
    
### （二）、基础知识之继承

    1.请用js实现一个类P，包含成员变量a，成员变量b，成员函数sum，sum输出a与b的和，a，b默认值都为0。实现一个类M，M继承自P，在P的基础上增加成员变量c，成员函数sum变成输出a,b,c的和。

* 答

```
function P(a,b){
    this.a = a;
    this.b = b;
}

P.prototype.sum = function(){
    return this.a + this.b;
}

function M(a,b,c){

    if(arguments.length < 3){
        if(arguments.length === 2){
            this.a = arguments[0];
            this.b = 0;
            this.c = arguments[1];
        } else if(arguments.length === 1){
            this.a = 0;
            this.b = 0;
            this.c = a;
        } else {

        }
    } else {
        P.call(this,a,b);
        this.c = c;
    }
    
}

M.prototype = new P();

M.prototype.sum = function(c){
    return this.a + this.b + this.c;
}

var m = new M(3);
console.log( m.sum() );

```

### （三）、基础知识之this

* this指向

```
    function F(){this.a=1;}
    
    F(); //指向window对象
    
    new F(); //指向new出来的对象
```
    
* 改变this指向

    原生js的方法 bind call apply方法。
    
    Es6中的 => 函数中，this的指向不会改变。
    
### （四）、基础知识之setTimeout

* 下列代码会输出什么？
    
```
for (var i = 0; i < 3; ++i) {
    function(i){
        setTimeout(function(){
            console.log(i);     
        }, 0);
    } 
}
    
    
//输出 333
//因为setTimeout是异步执行，同时限制条件是 ++i，不是i++。
```

* 或者面试官会问，setTimeout的时间设置为0，会有什么结果？

### （五）、基础知识之闭包

如果要让上面的代码正常输出 0 1 2，怎么做？

```
for (var i = 0; i < 3; ++i) {
    (function(i){
        setTimeout(function(){
            console.log(i);
        }, 0);
    })(i) 
}
```

### （六）、基础知识原生选择器有哪些？按照性能高低排序？

* 答：(不必全部答出)
 
```
a. document.getElementById()
    
b. document.getElementsByClassName()
    
c. document.getElementsByTagName()
    
d. document.querySelector()
    
f. document.querySelectorAll()

// 性能高低排序 ： d > f > b > c > a 
```
### （七）、自己实现一个Promise对象，你会怎么做？

* 答：（待补充）

### （八）、ES6中 Set和Map的区别

* 答：
 
Map : ES6 中两种新的数据结构集：Map 和 WeakMap。事实上每个对象都可以看作是一个 Map。
      一个对象由多个 key-val 对构成，在 Map 中，任何类型都可以作为对象的 key。
 
Set : Set 对象是一组不重复的值，重复的值将被忽略，值类型可以是原始类型和引用类型。

参考：[ES6 扫盲](https://github.com/metagrover/ES6-for-humans)


# 四、HTTP

###（一）、常见状态码

（介绍的文章太多了……列一下问的问题）

* 301 和 302的具体区别，都是重定向，返回一个新的链接，然后重新请求，差别在哪？

   答：301是永久性重定向，表示请求的资源已经分配到的新的URL。如果已经把资源对应的URL保存为书签了，应该重新保存。当指定资源路径最后忘了加 '/'，会出现301.
      
      302是临时性重定向，表示请求的资源已经被分配了新的url，希望用户本次使用新的url访问。已经移动的资源对应的url将来还有可能改变。
      
* 什么情况下会出现304？
* 400系列和500系列的区别？
* 如果出现500系列的问题，前端应该做什么？


###（二）、浏览器的缓存机制（与304状态码结合问）

参考腾讯文章 [web缓存机制系列](http://www.alloyteam.com/2012/03/web-cache-2-browser-cache/)


###（三）、HTTP HTTPS的区别。（非对称加密和对称加密的区别）



# 五、前端项目

### （一）、项目构建工具 gulp/webpack

1. gulp常用模块
 
答：

* gulp-rev: 给每个文件增加版本号，这个版本号是根据文件内容计算出的哈希码，用来解决浏览器自动缓存的问题
* gulp-useref: 代码压缩，合并多个文件

```
<!--build : css css/yourname.css-->
 //这里面是你的多个文件
<!--end build-->
```
* gulp-filter : 过滤器，筛选文件进行下一步
* gulp-uglify : 压缩js代码的模块
* gulp-csso : 压缩css代码插件
* gulp-watch : 监听文件改变，自动执行任务
* gulp-concat : 多个文件合并为一个文件
* gulp-responsive : 一个大图根据规则生成响应式图片

2.gulp压缩js的具体步骤：

答： 

* a. 新建一个 gulpfile.js 文件.
* b. 获取 gulp :   var gulp = require('gulp').
* c. 获取 gulp-uglify 组件
* d. 创建压缩任务

```
gulp.task('script', function() {

    // 1. 找到文件
    gulp.src('js/*.js')
    // 2. 压缩文件
        .pipe(uglify())
    // 3. 另存压缩后的文件
        .pipe(gulp.dest('dist/js'))
        
})
```

3.webpack压缩文件的具体步骤

4.gulp和grunt的工作原理

### （二）、项目优化方式：

* 答：雅虎军规 14条 

### （三）、CDN原理

* 答：与上题 一起参考课程：[雅虎军规](http://www.imooc.com/learn/50)

### （四）、除了雅虎军规，你还知道什么优化方式？

* 答：抱歉，这个我真的不知道。
### （五）、如何进行登陆检测？

* 答：在express框架中，使用session进行登陆检测。在用户登陆时，将前端传来的用户名和密码与数据库进行匹配，将匹配正确的用户的信息保存在服务端session中。在其他需要进行登陆检测的接口中，为其添加检测`req.session`的中间件，若`req.session`存在，则调用业务逻辑的处理，否则，返回错误信息，或重定向到登录页面。
