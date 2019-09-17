---
title: 初识Hexo
abbrlink: 97bd5563
date: 2019-08-28
tags:
  - hexo
  - 语法
categories: 基础
---
hexo的学习历程中，学习到的hexo语法以及一些技巧。
<!-- more  -->
最近在学习利用hexo来搭建个人博客，把学习过程中遇到的问题以及学习到的语法进行来总结，希望可以帮到其他小伙伴们。

### 新增post文章页面
命令行输入：```hexo new [layout] <title>```。
其中，```layout```指文章页面的布局，默认为post，可不输入。PS：可以通过修改 _config.yml 中的 default_layout 参数来指定默认布局。```title```指文章的标题，默认文件名称就是标题的名称。

### 标签插件
标签插件估计是最常用的一个语法，它是用于在文章中快速插入特定内容的插件，跟markdown语法中类似。

#### 引用块 - blockquote/endblockquote
语法如下：
```
{% blockquote [作者[, 其他资源信息]] [链接] [链接标题] %}
展示内容
{% endblockquote %}
```

示例：
```
{% blockquote sugarZ, 程序圆 http://localhost:4000/sugarZ/2019/08/27/first-realize/ sugarZ的博客 %}
展示内容
{% endblockquote %}
```

{% blockquote sugarZ, 程序圆 http://localhost:4000/sugarZ/2019/08/27/first-realize/ sugarZ的博客 %}
展示内容
{% endblockquote %}

#### 代码块 - codeblock/endcodeblock
语法如下：
```
{% codeblock [标题] [lang:language] [链接] [链接title] %}
code snippet
{% endcodeblock %}
```
代码块的语法除了hexo特有的这种，还有就是markdown中的反引号语法，效果一样，反引号语法如下：
``` 
``` [language] [title] [url] [link text] code snippet ```
```

示例：
{% codeblock %}
alert('Hello World!')
{% endcodeblock %}

#### Pull Quote
语法：
```
{% pullquote [class] %}
content
{% endpullquote %}
```

示例：
{% pullquote %}
content
{% endpullquote %}

#### 插入图片 - Image
在文章中插入图片，可自定义图片宽高，语法：
```
{% img [class names] /path/to/image [width] [height] "title text 'alt text'" %}
```

示例：
{% img /path/to/image 100 20 "ceshi" %}

#### 文章中插入链接 - Link
在文章中插入链接，并自动给外部链接添加```target="_blank"```属性，语法：
```
{% link
链接文案 链接url [external] [title]
%}
```

示例：
{% link
text http://localhost:4000/sugarZ/2019/08/27/first-realize/
%}

#### 实现段落文本缩进
可以在需要缩进的段落文本前添加```&nbsp;&nbsp;&nbsp;```，来实现段落文本的缩进。每一个```&nbsp;```代表一个空格的距离。
