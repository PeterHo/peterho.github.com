---
layout: post
title: Atom编辑器使用入门(一)
date: '2015-12-18 16:29'
---

原创时间:2015-12-18
更新时间:2015-12-21

# 为什么选择使用Atom
Atom是GitHub推出的一款编辑器,被称为21世纪的黑客编辑器,主要的特点是现代,易用,可定制.
我之前也用过多款编辑器,现总结一下个人对各编辑器的看法:
Vim是我用的时间最长也是折腾时间最长的编辑器,优点是逼格高,定制性强,编辑效率高,资源占用少,还可以终端操作,缺点是学习曲线陡峭,经常出一些莫名其妙的错误,突然就是一堆调试信息闪过,长得最丑,哪怕是使用了各种插件美化,还是最丑,自身特性太少,过于依赖插件,如果要实现最基本的IDE的功能,需要装一大堆插件
Emacs的优点是功能强大,啥都可以实现,因为他本身就是个操作系统啊,缺点是入门门槛高,我当时为了用Emacs还学了两大本关于Emacs和Lisp的书呢,但是我个人觉得它最大的问题就是快捷键太反人类,特别是在用笔记本时手指真的受不了...
SublimeText:长得很漂亮,至少在它刚出来时算是最漂亮的编辑器了,自带一些编辑器应该有的功能,使得不需要怎么配置就能上手.缺点是闭源,收费,Vim模式的光标太丑,对中文支持不好,都出来几年了Linux下还是连中文都打不出来(虽然可以通过某些方法解决,但一定程度上能说明作者对中国用户的态度,这也是闭源表现出来的一个问题),
VSCode:微软推出的编辑器,前段时间刚开源了,感觉和Atom很像,我很看好这款编辑器,但现在的问题是出来的时间太短,功能和插件不够丰富,生态圈还没有形成,也许再过两年会统治世界呢
Atom跟上面的编辑器比起来优点就是比较均衡,上手简单,零门槛,资源占用不高,自身支持的功能就挺多,配置起来也很方便,还有一大堆插件可以选择,还开源免费呢,而且在对中文的支持上也没什么问题.

# 安装
# 主页
- [官网](https://atom.io/)
- [插件](https://atom.io/packages/list)
- [主题](https://atom.io/themes/list)

# 插件

```

apm install vim-mode

apm install atom-beautify

apm install linter

apm install emmet

apm install file-icons

apm install color-picker

apm install git-plus

apm install project-manager

apm install highlight-line
```

# 配置
- 配置文件

> ~/.atom/config.cson

> ~/.atom/keymap.cson

> ~/.atom/init.coffee

# 快捷键
## 显示列表

```

Ctrl+Shift+P        显示命令列表



Ctrl+T              显示文件列表

Ctrl+B              显示已打开文件列表

Ctrl+Shift+B        显示未同步文件列表



Ctrl+R              显示当前文件符号列表

Ctrl+Shift+R        显示工程内符号列表(需要tags文件)
```

## 搜索

```

Ctrl+F              文件内搜索

Ctrl+Shift+F        工程内搜索
```

## 分栏

```

Ctrl+K 右/下         新建分栏

Ctrl+K Ctrl+右/下    切换分栏焦点

Ctrl+W              关闭分栏
```

## 折叠

```

Ctrl+Alt+[/]        折叠/展开

Ctrl+Alt+Shift+{/}  全局折叠/展开

Ctrl+K Ctrl+n       折叠n层
```

## 配置

```

Ctr+,               显示配置选项
```

## TreeView

```

Ctrl+0          切换TreeView焦点

Ctrl+\          切换TreeView显示



a               添加文件

m               移动文件

delete          删除文件
```
