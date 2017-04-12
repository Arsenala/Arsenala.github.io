---
layout:     post
title:      "前端面试题答案"
subtitle:   "WebInterview-01"
date:       2017-02-21 22:00:00
author:     "xiaochao"
header-img: "img/post-bg-ios9-web.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 前端开发
    - 面试答案
---

### 1.Html5 为什么只需要写<!DOCTYPE HTML>?
HTML5不基于SGML，因此不需要对DTD进行引用，但是需要DOCTYPE来规范浏览器的行为（让浏览器按照他们应该的方式来运行）而HTML4.01基于SGML，所以需要对DTD进行引用，才能告知浏览器文档使用的文档类型。
### 2.行内元素有哪些？块级元素又哪些？空（void）元素有哪些？
行内元素：a b span img input select strong
块级元素：div ul ol li dl dt dd h1 h2 h3 h4 p
空元素：br hr img link meta
### 3.页面导入样式时，使用link和@import有什么区别？
link属于XHTML标签，而@import是CSS提供的；
页面被加载时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载；
@import只在IE5以上才能识别，而link是XHTML标签，无兼容问题；
link方式的样式的权重高于@import的权重。
### 4.HTML5有哪些新特性，移除了哪些元素？如何处理HTML5新标签的浏览器兼容问题？
新增元素
内容元素：article footer header nav section
表单元素：calendar date time email url search 
控件元素：webworker websockt Geolocation
移除元素
显示层元素：basefont big center font s strike tt u
性能较差元素：frame frameset noframes
处理兼容问题的两种方式
IE6/IE7/IE8支持通过document方法产生的标签，利用这一特性让这些浏览器支持HTML5新标签。
使用是HTML5shim框架，另外，DOCTYPE声明的方式是区分HTML和HTML5标志的一个重要因素，此外，还可以根据新增的结构，功能元素来加以区分。
### 5.如何区分HTML和HTML5
（1）在文档类型声明上不同：
HTML是很长的一段代码，很难记住，而HTML5却只有简简单单的声明，方便记忆。
（2）在结构语义上不同：
HTML：没有体现结构语义化的标签，通常都是这样命名的< div id="header" >< /div >
### 6.简述一下你对HTML语义化的理解？
（1）用正确的标签做正确的事情。
（2）HTML语义化让页面的内容结构化，结构更清晰，便于浏览器，搜索引擎解析。
（3）即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的。
（4）搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO。
（5）使用源代码的人对网站更容易将网站分块，便于阅读维护理解。
### 7.HTML5的离线存储怎么使用，工作原理能不能解释一下
localStorage 长期存储数据，浏览器关闭后数据不丢失。
sessionStorage 数据在浏览器关闭后自动删除。
### 8.iframe有哪些缺点？
（1）在网页中使用框架结构最大的弊端是搜索引擎的“蜘蛛”程序无法解读这种页面。
（2）框架结构有时会让人感到迷惑，页面很混乱。
### 9.Doctype作用？严格模式与混合模式如何区分？它们有何意义？
（1）< !Doctype >声明位于文档中的最前面，处于< html >标签之前，告知浏览器的解析器，用什么文档类型规范来解析这个文档。
（2）严格模式的排版和JS运作模式是以该浏览器支持的最高标准运行。
（3）在混杂模式中，页面以宽松的向后兼容的方式显示，模拟老式浏览器的行为以防止站点无法工作。
（4）DOCTYPE不存在或格式不正确会导致文档以混杂模式呈现。
### 10.常见兼容性问题？
（1）png24位的图片在IE6浏览器上出现背景
解决方案是：做成PNG8。
（2）浏览器默认的margin和padding不同
解决方案是：加上一个全局*{ margin：0；padding：0；}来统一。
（3）IE6双边距bug：块属性标签float后，又有横行的margin情况下，在IE6显示margin比设置的大。浮动IE产生的双倍距离#box{ float:left;width:10px;margin:0 0 0 100px;}这种情况下IE6会产生200px的距离
解决方案是：加上display：inline，使浮动忽略。
（4）IE下，可以使用获取常规属性的方法来获取自定义属性，也可以使用getAttribute（）获取自定义属性；Firefox下，只能使用getAttribute（）获取自定义属性
解决方案是：统一通过getAttribute（）获取自定义属性。
（5）IE下，even对象有X，Y属性但是没有pageX，pageY属性
解决方案是：缺点是在IE浏览器下可能会增加额外的HTTP请求。
（6）Chorme中文界面下默认会将小于12px的文本强制按照12px显示
解决方案是：可通过加入CSS属性-webkt-text-size-adjust：none解决。
（7）超链接访问过后hover样式就不出现了，被点击访问过的链接样式不在具有hover和active
解决方案是：改变CSS属性的排列顺序：
a：link{} a：visited{} a:hover{} a:active{}。












