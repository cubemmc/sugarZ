---
title: 初识Hexo
updated: 2019-08-27 10:00:10
tags:
---

最近在学习利用hexo来搭建个人博客，把学习过程中遇到的问题以及学习到的语法进行来总结，希望可以帮到其他小伙伴们。

hexo的语法大多数和markdown语法都一样，不过也有个别比较特殊的存在。

### 1、标签插件 - 引用块和代码块的使用
标签插件估计是最常用的一个语法，它是用于在文章中快速插入特定内容的插件。跟markdown语法中类似，就是引入引用块或者代码块，突出或者高亮显示某部分内容。

#### 引用块
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

#### 代码块
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
```
{% codeblock [标题] [lang:language] [链接] [链接title] %}
alert('Hello World!')
{% endcodeblock %}
```

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

#### Image
在文章中插入指定宽高的图片，语法：
```
{% img [class names] /path/to/image [width] [height] "title text 'alt text'" %}
```

示例：
{% img /path/to/image 100 20 "ceshi" %}

#### Link
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

#### Link
{% raw %}
content
{% endraw %}