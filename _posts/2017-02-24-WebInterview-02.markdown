---
layout:     post
title:      "前端面试题答案"
subtitle:   "WebInterview-02"
date:       2017-02-24 12:00:00
author:     "xiaochao"
header-img: "img/post-bg-ios9-web.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 前端开发
    - 面试答案
---

### 11、如何实现浏览器内多个标签页之间的通信？
调用localstorge、cookies等本地存储方式
### 12、webSocket如何兼容低浏览器？
Adobe Flash Socket 、 ActiveX HTMLFile (IE) 、 基于 multipart 编码发送 XHR 、 基于长轮询的 XHR
### 13、支持HTML5新标签
（1）IE8/IE7/IE6支持通过 document.createElement 方法产生的标签，可以利用这一特性让这些浏览器支持 HTML5 新标签，浏览器支持新标签后，还需要添加标签默认的样式；
（2）当然最好的方式是直接使用成熟的框架、使用最多的是 html5shim 框架
< !--[if lt IE 9] >

< script > src="http://html5shim.googlecode.com/svn/trunk/html5.js"< script >

< ![endif]-- >;
### 14、如何区分：DOCTYPE 声明\新增的结构元素\功能元素，语义化的理解？
（1）用正确的标签做正确的事情；
（2）html语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析；
（3）在没有样式 CSS 情况下也以一种文档格式显示，并且是容易阅读的；
（4）搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，利用 SEO ；
（5）使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。
### 15、介绍一下 CSS 的盒子模型？
（1）有两种，IE 盒子模型、标准 W3C 盒子模型； IE 的 content 部分包含了 border 和 padding；
（2）盒模型：内容（content）、填充（padding）、边界（margin）、边框（border）。
### 16、CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3 新增伪类有哪些？
（1）id 选择器（#myid）
（2）类选择器（.myclassname）
（3）标签选择器（div，h1，p）
（4）相邻选择器（h1 + p）
（5）子选择器（ul > li）
（6）后代选择器（li a）
（7）通配符选择器（\* ）
（8）属性选择器（ a[rel = "external"]）
（9）伪类选择器（a: hover, li: nth - child）
### 17、可继承的样式：
 font-size font-family color, UL LI DL DD DT
### 18、不可继承的样式：
border padding margin width height
### 19、优先级就近原则，同权重情况下样式定义最近者为准 
### 20、载入样式以最后载入的定位为准
优先级为: !important > id > class > tag;important 比 内联优先级高 
### 21、CSS3新增伪类举例：
p:first-of-type  选择属于其父元素的首个< p >元素的每个< p >元素；
p:last-of-type  选择属于其父元素的最后< p >元素的每个< p >元素；
p:only-of-type  选择属于其父元素唯一的< p >元素的每个< p >元素；
p:only-child  选择属于其父元素的唯一子元素的每个< p >元素；
p:nth-child  选择属于其父元素的第二个子元素的每个< p >元素；
p:enabled  :disabled 控制表单控件的禁用状态；
p:checked  单选框或复选框被选中。
### 22、如何居中div？如何居中一个浮动元素？
给div 设置一个宽度，然后添加 margin:0 auto 属性；div{width:200px; margin:0 auto; }
### 23、居中一个浮动元素
确定容器的宽高  宽500 高300的层，设置层的外边距
.div{width:500px;height:300px;margin:-150px 0 0 -250px;position:relative;background:green；left：50%；头：50%}
### 24、css3有哪些新特性？
CSS3 实现圆角（border-radius:8px;），阴影（box-shadow:10px）,对文字加特效（text-shadow）,线性渐变（gradient），旋转（transform）
transform:rotate(9deg) scale(0.85,0.90) translate(0px,-30px) skew(-9deg,0deg);//旋转，缩放，定位，倾斜
增加了更多的 css 选择器 多背景 rgba
### 25、为什么要初始化 CSS 样式
因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对 CSS 初始化往往会出现浏览器之间的页面显示差异。
当然，初始化样式会对 SEO 有一定的影响，但鱼和熊掌不可兼得，但力求影响最小的情况下初始化。
最简单的初始化方法是：\*{padding:0;margin:0} (不建议)
淘宝的样式初始化：
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin:0; padding:0; }

body, button, input, select, textarea { font:12px/1.5tahoma, arial, \5b8b\4f53; }

h1, h2, h3, h4, h5, h6{ font-size:100%; }

address, cite, dfn, em, var { font-style:normal; }

code, kbd, pre, samp { font-family:couriernew, courier, monospace; }

small{ font-size:12px; }

ul, ol { list-style:none; }

a { text-decoration:none; }

a:hover { text-decoration:underline; }

sup { vertical-align:text-top; }

sub{ vertical-align:text-bottom; }

legend { color:#000; }

fieldset, img { border:0; }

button, input, select, textarea { font-size:100%; }

table {border-collapse:collapse;border-spacing:0;} 
### 26、display:inline-block 什么时候会显示间隙？
移除空格，使用margin 负值、使用 font-size:0、letter-spacing 、word-spacing
### 27、使用 CSS 预处理器吗？喜欢哪个？
SASS




