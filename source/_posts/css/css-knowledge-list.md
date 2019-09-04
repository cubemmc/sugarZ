---
title: 你不知道的css小知识
abbrlink: a6497cb5
date: 2019-08-30 16:34:51
tags:
  - css
categories: css
---
你不知道的css小知识。
<!-- more -->
本文章总结了一些常用或者不常用的css技巧知识，并且将会持续更新。

#### 图片点击穿透
&nbsp;&nbsp;&nbsp;一张图片覆盖在了另一张图片上，需要穿透上面的图片，实现底层图片的点击事件，可以在上层图片的样式中添加样式`pointer-events: none;`,可以实现这个效果。该css属性在大多数浏览器下都可用，通用性比较强，具体可参考下图（图片资源来源于[canIuse网站查询](https://www.caniuse.com/#search=pointer-events)）：
{% img /img/pointer_events_use.jpg "pointer-events可用浏览器" %}

#### 英文单词换行
&nbsp;&nbsp;&nbsp;可以设置文本的样式为`word-break:break-all`，来实现英文单词换行的效果，且不管是什么字符，都是本行放不下就直接换行。该css属性在国内浏览器都可使用，只要浏览器内核版本不是特别低，都是可用的，所以放心大胆的用吧。

#### white-space
white-space包含以下五种属性：
>* normal：默认属性，合并空白字符和换行符。意思就是看见连续的空格或回车，一律处理成单个空格。
>* pre：空格字符不合并，并且内容只有在有换行符的地方换行，也就是自动换行的能力消失。
>* nowrap：和normal一样会合并空白字符，但不允许文本换行。
>* pre-wrap：空白字符不合并，并且内容会在有换行符的地方换行，也支持自动换行。
>* pre-line：空白字符合并，内容支持自动换行和手动换行。

#### 不可思议的纯css滚动进度条效果
利用线性渐变来实现css的滚动条效果，来源于[纯css滚动进度条的实现[作者：chokcoco]](https://juejin.im/post/5c35953ce51d45523f04b6d2)

#### 如何设置文本两端对齐？
实现效果如下：
{% img /img/text_align_last.jpg 150 200 %}

具体实现方法可查看：[文本两端对齐](https://codepen.io/cubemmc/pen/yLBPJPr)
