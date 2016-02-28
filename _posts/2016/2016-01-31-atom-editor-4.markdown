---
layout: post
title: Atom编辑器入门到精通(四)  Atom使用进阶
date: '2016-02-29 10:29'
---

原创时间:2016-01-31<br>更新时间:2016-02-27

在本节中将介绍Atom提供的更高级的使用技巧,通过这些技巧将会进一步提高你的代码编写效率
# 代码片段(Snippets)
Snippets是一种在代码中快捷插入代码块的方式,下面是维基百科中对Snippet的解释
>片段（Snippet）是一个编程用语，指的是源代码、机器码、文本中可重复使用的小区块。通常它们是有正式定义的执行单位，以纳入更大的编程模块。片段经常用来明晰其他“凌乱”函式的功用，或尽量减少使用与其他函式共用的重复代码。
片段管理是某些文本编辑器、程式源代码编辑器、IDE、与相关软件的其中一项功能。其使得使用者能够在反复的编辑作业中保持和使用这些片段。

让我们通过一个实验来感受一下Snippets给我们带来的便利体验
1. 打开Atom编辑器
2. 使用`Ctrl+N`新建一个文件
3. 使用`Ctrl+S`保存文件,将文件名改为`new.html`
4. 在`new.html`中键入`html`四个字符,然后按`tab`键,这时你会发现`html`这段文本被扩展成了
```
<html>
  <head>
    <title></title>
  </head>
  <body>

  </body>
</html>
```
并且光标被移到了`<title>`标签之间,方便你直接输入这个html文件的标题
5. 在`<title>`标签之间输入完成html页面标题以后,再次键入`tab`键
你会发现光标又被移到了`<body>`标签下面了

这就是Snippets,它让你可以很方便地通过一个关键词来插入一段代码块,并且还能通过`tab`键在这段代码块的输入点之间移动光标,达到快速编码的目的
不同类型的文件有不同的Snippets,你可以通过快捷键`Alt+Shift+S`来列出当前文件所提供的所有的Snippets

![Snippet](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_4/snippets.png)

## 自定义Snippets
Atom中有很多插件都提供了对某个特定文件中Snippets的支持,比如上面的`html`Snippets,就来自`language-html`插件
当然我们也可以定义自己的Snippets,这样可以在编码的过程中更加灵活地使用这个特性





# 自动补全

# 代码折叠

# 分栏

# 代码类型
