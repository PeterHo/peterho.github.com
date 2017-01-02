---
layout: post
title: Atom编辑器入门到精通(一) 安装及使用基础
date: '2015-12-18 16:29'
---

原创时间:2015-12-18
更新时间:2016-12-08

# 为什么选择使用Atom
Atom是GitHub推出的一款编辑器, 被称为21世纪的黑客编辑器. 其主要的特点是现代, 易用, 可定制.
本人以前用过多款编辑器, 现在来总结一下个人对各编辑器的看法:

Vim是我使用最久也是最折腾的编辑器
其优点是逼格高, 定制性强, 编辑效率高, 资源占用少, 还可以终端操作
缺点是学习曲线陡峭, 经常出一些莫名其妙的错误, 或者就是突然一大堆调试信息闪过, 长得最丑, 哪怕是使用了各种插件美化, 还是最丑.
另外就是自身的现代化特性太少, 过于依赖插件, 如果要实现最基本的IDE的功能, 需要装一大堆插件, 插件本身的质量和相互之间的兼容性也是个问题.

Emacs的优点是功能强大, 啥都可以实现, 因为他自己本来就是个操作系统嘛.
缺点是入门门槛高, 我当时为了用Emacs还看了两大本关于Emacs和Lisp的书. 但我个人觉得它最大的问题是快捷键太反人类, 特别是在用笔记本时手指真的受不了...

SublimeText
长得很漂亮, 至少在它刚推出时算得上是最漂亮的编辑器之一了, 自带一些编辑器应该有的功能, 使得不需要怎么配置就能上手.
缺点是闭源, 收费, Vim模式的光标太丑, 对中文支持不好, 都推出好几年了还是无法在Linux下输入中文(虽然可以通过某些方法解决, 但一定程度上能说明作者对中国用户的态度, 这也是闭源导致的一个问题).

VSCode
微软推出的编辑器, 前段时间刚开源了, 感觉和Atom很像. 这是我很看好的一款编辑器, 但现在的问题是发布的时间太短, 功能和插件不够丰富, 生态圈还没有形成, 不过仗着牛逼的老爸, 也许再过两年会统治世界呢.

Atom跟上面的编辑器比起来优点是比较均衡, 上手简单, 零门槛, 资源占用不高, 自身支持的功能就挺多, 配置起来也很方便, 还有一大堆插件可以选择, 还开源免费呢, 而且在对中文的支持上也没什么问题.

本教程主要参考Atom的[官方文档](https://atom.io/docs) 1.12.6版, 教程中所用的很多图片也取自那里, 在后文中就不一一注明了.

本教程在Linux环境下编写, 其中涉及的快捷键和其他特性都在Linux Mint下测试通过.

# 安装
打开[官方主页](https://atom.io/)
![官方主页](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_1/linux-downloads.png)
网页会自动判断你的操作系统, 给出其对应的下载按钮
比如我的系统是Linux, 就可以点击`Download .deb`按钮来下载系统对应的安装包
如果要下载其他系统的安装包, 点击`Other platforms`链接即可
## Mac
解压下载的zip安装包后, 将解压出的`Atom`应用拖到应用目录下
或者通过Homebrew Cask安装
```
brew cask install atom
```

## Windows
运行安装包安装

## Linux
如果是基于Debian的发行版, 执行命令:
```
sudo dpkg -i atom-amd64.deb
```
如果是RedHat, 则执行:
```
rpm -i atom.x86_64.rpm
```

安装完成后运行Atom, 将会看到这样的界面, 说明我们已经安装成功了
![界面](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_1/first-launch.png)


# 基本使用
## 命令面板
Atom的很多功能学习和参考了其他优秀的编辑器, 命令面板就是其一.
当你第一次看到它时, 还以为在用Sublime呢
命令面板是Atom中最常用的功能之一, 当你在编辑器中使用快捷键`Ctrl+Shift+P`时, 就会看到它
![控制面板](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_1/command-palette.png)
在控制面板中可以输入Atom中和插件中定义的所有命令, 并且支持模糊搜索
比如说当你输入cboo时, 所有包含有这4个字符的命令就都列出来了
在列出的命令后还显示了此命令对应的快捷键(如果有的话)

## 设置窗口
自带可视化的设置界面是Atom使用很方便的原因之一, 而不像传统的编辑器那样需要手动修改配置文件.
![设置窗口](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_1/settings.png)
你可以使用下面三种方法来打开设置窗口
1. 主菜单`Edit`->`Preferences`
2. 在命令面板中输入命令`Settings View:Open`. 因为命令窗口支持模糊查询, 因此只需要输入`svo`, 就可以了
3. 使用快捷键`Ctrl+,`

在设置窗口中可以设置和管理各种编辑器行为, 键盘快捷键, 插件, 主题等内容

### 设置窗口界面主题和代码高亮
Atom自带了4种窗口主题和8种代码高亮方式
可以通过设置窗口中的Themes页面来配置和修改
另外还有n多n多第三方制作的主题可以安装,安装方法在后面会讲到
![主题设置](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_1/theme.png)

## 文件操作
### 打开文件
你可以通过主菜单`File`->`Open File...`或者快捷键`Ctrl+O`来打开文件选择窗口
![打开文件](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_1/open-file.png)

### 保存文件
主菜单 `File`->`Save`
快捷键 `Ctrl+S`
另存为: `Ctrl+Shift+S`
保存所有文件: `File`->`Save All`

### 打开文件夹
打开文件夹是一个很实用的功能, 可以像IDE一样打开一个项目的根目录
可以通过在主菜单选择`File`->`Add Project Folder...`来打开或者添加一个目录,也可以使用快捷键`Ctrl+Alt+O`.
在打开一个文件夹以后该文件夹下的所有子目录和文件就会如下图一样以目录树的方式显示在主窗口左边
![打开文件夹](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_1/project-view.png)
你可以通过在目录树栏中右键菜单或选中文件时使用快捷键`a`,`m`,`delete`来对文件进行新建,重命名,删除等操作
如果要切换目录树栏的显示与隐藏可以使用快捷键`Ctrl+\`或输入命令`Tree View:Toggle`
目录树中右键菜单中还能实现文件的复制粘贴等功能

### 查找文件
当打开一个或多个目录时,你可以:
* 通过`Ctrl+T`或`Ctrl+P`来搜索目录中的文件
* 通过`Ctrl+B`来搜索一个当前打开的文件
* 通过`Ctrl+Shift+B`来搜索一个新建的或更改过的文件

当然这些功能也都支持模糊查询
如果你需要在搜索时过滤掉一些特定的文件(比如.pyc文件)或目录(比如.git), 可以配置`core.ignoredNames`和`fuzzy-finder.ignoredNames`.
也可以通过配置`core.excludeVcsIgnoredPaths`来过滤掉在.gitignore中配置的文件.
具体的配置方法以后会讲到.


# 总结
在本文中我们学习了如何安装Atom和一些基本的使用方法, 在学习了这部分内容以后相信你已经可以方便地使用Atom了
在以后的课程中我们会学习一些Atom更高级的用法, 让我们使用得更方便更流畅.
