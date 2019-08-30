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
#### 图片点击穿透
一张图片覆盖在了另一张图片上，需要穿透上面的图片，实现底层图片的点击事件，可以在上层图片的样式中添加样式`pointer-events: none;`,可以实现这个效果。

#### 英文单词换行
可以设置文本的样式为`word-break:break-all`，来实现英文单词换行的效果，且不管是什么字符，都是本行放不下就直接换行。

#### white-space
white-space包含以下五种属性：
>* normal：默认属性，合并空白字符和换行符。意思就是看见连续的空格或回车，一律处理成单个空格。
>* pre：空格字符不合并，并且内容只有在有换行符的地方换行，也就是自动换行的能力消失。
>* nowrap：和normal一样会合并空白字符，但不允许文本换行。
>* pre-wrap：空白字符不合并，并且内容会在有换行符的地方换行，也支持自动换行。
>* pre-line：空白字符合并，内容支持自动换行和手动换行。

#### 不可思议的纯css滚动进度条效果
[纯css滚动进度条的实现](https://juejin.im/post/5c35953ce51d45523f04b6d2)
[一个充满css灵感的地方](https://chokcoco.github.io/CSS-Inspiration/#/./others/1px-line)