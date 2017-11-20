# ldF2E-widgets
本手册指导开发领动平台相关组件



基本原则
结构、样式、行为分离
尽量确保文档和模板只包含 HTML 结构，样式都放到样式表里，行为都放到脚本里。
缩进
统一两个空格缩进（总之缩进统一即可），不要使用 Tab 或者 Tab、空格混搭。
文件编码
使用不带 BOM 的 UTF-8 编码。
•	在 HTML中指定编码 <meta charset="utf-8"> ；
•	无需使用 @charset 指定样式表的编码，它默认为 UTF-8 （参考 @charset）；
一律使用小写字母

<!—推荐 -->
<img src="google.png" alt="Google">

<!—不 推荐 -->
<A HREF="/">Home</A>

/* 推荐 */
color: #e5e5e5;

/* 不推荐*/
color: #E5E5E5;


省略外链资源 URL 协议部分
省略外链资源（图片及其它媒体资源）URL 中的 http / https 协议，使 URL 成为相对地址，避免Mixed Content 问题，减小文件字节数。
其它协议（ftp 等）的 URL 不省略。
<!-- Recommended -->
<script src="//www.w3cschool.cn/statics/js/autotrack.js"></script>

<!-- Not recommended -->
<script src="http://www.w3cschool.cn/statics/js/autotrack.js"></script>

/* Recommended */
.example {
  background: url(//www.google.com/images/example);
}

/* Not recommended */
.example {
  background: url(http://www.google.com/images/example);
}
统一注释
通过配置编辑器，可以提供快捷键来输出一致认可的注释模式
HTML 注释
•	模块注释
•	<!-- 文章列表列表模块 -->
•	<div class="article-list">
•	...
</div>
•	区块注释
•	<!--
•	@name: Drop Down Menu
•	@description: Style of top bar drop down menu.
•	@author: Ashu(Aaaaaashu@gmail.com)
•	-->
CSS 注释
组件块和子组件块以及声明块之间使用一空行分隔，子组件块之间三空行分隔；
/* ==========================================================================
   组件块
 ============================================================================ */

/* 子组件块
 ============================================================================ */
.selector {
  padding: 15px;
  margin-bottom: 15px;
}

/* 子组件块
 ============================================================================ */
.selector-secondary {
  display: block; /* 注释*/
}

.selector-three {
  display: span;
}
JavaScript 注释
单行注释
必须独占一行。// 后跟一个空格，缩进与下一行被注释说明的代码一致。
多行注释
避免使用 /*...*/ 这样的多行注释。有多行注释内容时，使用多个单行注释。
•	函数/方法注释
•	函数/方法注释必须包含函数说明，有参数和返回值时必须使用注释标识。；
•	参数和返回值注释必须包含类型信息和说明；
•	当函数是内部函数，外部不可访问时，可以使用 @inner 标识；
/**
 * 函数描述
 *
 * @param {string} p1 参数1的说明
 * @param {string} p2 参数2的说明，比较长
 *     那就换行了.
 * @param {number=} p3 参数3的说明（可选）
 * @return {Object} 返回值描述
 */
function foo(p1, p2, p3) {
    var p3 = p3 || 10;
    return {
        p1: p1,
        p2: p2,
        p3: p3
    };
}
文件注释
文件注释用于告诉不熟悉这段代码的读者这个文件中包含哪些东西。 应该提供文件的大体内容, 它的作者, 依赖关系和兼容性信息。如下:
/**
 * @fileoverview Description of file, its uses and information
 * about its dependencies.
 * @author user@meizu.com (Firstname Lastname)
 * Copyright 2015 Meizu Inc. All Rights Reserved.
 */
 
 ## 其中包含五大部分

### 1.组件css规范
### 2.组件js规范
### 3.组件后台设置功能开发规范
### 4.组件前台展示功能开发规范
### 5.组件测试项
### 6.其他参考项
