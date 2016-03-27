---
layout: post
title: Atom编辑器入门到精通(四)  Atom使用进阶
date: '2016-02-29 10:29'
---

原创时间:2016-01-31<br>更新时间:2016-03-27

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
在Atom的配置目录(如果是Linux系统,这个目录是`~/.atom`)下包含一个名为`snippets.cson`的文件,这个文件就负责保存我们的自定义Snippets.你可以通过主菜单`Edit`->`Open Your Snippets`来方便地打开这个文件.
### Snippet配置格式
基本的Snippet的格式是这样的
```
'.source.js':
  'console.log':
    'prefix': 'log'
    'body': 'console.log(${1:"crash"});$2'
```
配置的第一行指定该Snippet应用的文件类型,获得文件类型字符串最简单的方式是查看该文件对应的语言插件的Scope项
举个例子,如果你想为Java文件添加一个Snippet项,你需要在设置页面查看`language-java`插件的插件信息,你可以看到插件信息的第一排`Scope`的值为`source.java`,因此Java文件的文件类型字符串就是一个点号`.`接上`source.java`(就像CSS的类选择器一样)

![SnippetScope](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_4/snippet-scope.png)

配置的第二行是Snippet的名字,最好取一看就能猜出该Snippet的作用的那种名字.
接下来的`prefix`指明触发该Snippet的字符串
`body`的值`'console.log(${1:"crash"});$2'`指明触发的Snippet的具体内容
其中每个接着数字的`$`表示一个插入项,当用户按`tab`时,光标会在设置的插入项之间移动

总结一下,上面的例子会给JavaScript文件添加一个`log`snippet
当在js文件中输入`log`并按`tab`,它会被扩展为
```
console.log("crash");
```
`"crash"`字符串会被选中,因此如果直接输入其他字符就能改变`"crash"`这个字符串,当在次按下`tab`时,光标又会跳到这一行的末尾`;`后面.

### 配置多行的Snippet
多行的Snippet配置如下,就是用`"""`符号将一段body包起来
```
'.source.js':
  'if, else if, else':
    'prefix': 'ieie'
    'body': """
      if (${1:true}) {
        $2
      } else if (${3:false}) {
        $4
      } else {
        $5
      }
    """
```

### Snippet的Snippet
当你在`snippets.cson`中配置Snippet时,可以使用`snip`和`snipns`Snippet来插入新的Snippet片段


# 自动补全
Atom自带了基本的自动补全功能
![AutoComplete](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_4/autocomplete.png)
默认情况下Atom会根据当前文档的内容来自动补全
如果你想要更多的选项,可以在`autocomplete-plus`插件设置处设置.比如可以设置该插件通过所有打开的文档来补全(而不仅仅是当前文档)

# 代码折叠
代码折叠在查看或编写代码时非常有用,Atom同样也支持这个功能
你可以通过点击行号旁边的箭头或使用快捷键`Ctrl+Alt+[`和`Ctrl+Alt+]`来折叠或展开代码
![Folding](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_4/folding.png)
另外你还可以通过`Ctrl+Alt+Shift+[`和`Ctrl+Alt+Shift+]`来折叠或展开全部代码
通过`Ctrl+K Ctrl+Num`来指定折叠哪一层缩进(`Num`指定缩进的深度)
通过`Ctrl+Alt+F`来折叠任意选中的代码段


# 分栏
![Panes](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_4/panes.png)
你可以使用`Ctrl+K 方向键`来创建新的分栏,其中方向键的方向决定了分栏的方式,比如`Ctrl+K ↓`就会创建一个新的水平分栏
当已经存在分栏时,通过`Ctrl+K Ctrl+方向键`来在分栏间切换光标焦点.
如果你想关闭一个分栏,使用`Ctrl+W`


# 代码类型
Atom会自动识别你当前编辑的文件的类型
如果识别失败,Atom会将此文件当做普通的文本文档来处理
在这种情况下我们可以使用`Ctrl+Shift+L`来手动指定或改变当前文件的类型
![Grammar](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_4/grammar.png)
