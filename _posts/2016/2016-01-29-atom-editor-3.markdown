---
layout: post
title: Atom编辑器入门到精通(三) 文本编辑基础
date: '2016-02-29 10:29'
---

原创时间:2016-02-29<br>更新时间:2016-02-29


身为编辑器,文本编辑的功能自然是放在第一位的,此文将总结常用的文本编辑的方法和技巧,掌握这些技巧以后可以极大地提高文本编辑的效率


## 配置
Atom的配置文件位于HOME目录的.atom文件夹下<br>
主要的配置文件有:

`~/.atom/config.cson`

主要的配置文件

`~/.atom/keymap.cson`

快捷键的配置文件

`~/.atom/init.coffee`
每当Atom有新窗口建立时都会调用此文件



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
