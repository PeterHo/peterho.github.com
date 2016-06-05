---
layout: post
title: Atom编辑器入门到精通(五) Git支持
date: '2016-04-10 19:38'
---

原创时间:2016-04-10<br>更新时间:2016-06-05

版本控制对于开发来说非常重要,Atom当然也提供了很好的支持,本文将介绍如何在Atom中集成使用Git和GitHub

# 恢复文件
当你修改了某个文件,然后发现改得不满意,希望恢复文件到最后一次提交的状态,可以使用`Cmd+Alt+Z`或`Checkout Head Revision`命令
此命令将会放弃你对文件所有的修改,直接将文件恢复为最后一次提交的版本
相当于Git命令`git checkout HEAD -- filename`和`git reset HEAD -- filename`
![Checkout](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_5/git-checkout-head.gif)
如果恢复文件后发现还是改过以后的好,可以使用`Cmd+Z`来撤销刚才的修改

# 显示状态
在前文中讲过,我们可以通过`Cmd+T`/`Cmd+P`列出所有项目中的文件,或`Cmd+B`列出所有当前打开的文件,
或是`Cmd+Shift+B`来列出所有新建的或更改过的文件
所有的这些方法都会在弹出的文件列表的右边以图标的形式显示文件的状态
特别是`Cmd+Shift+B`,它会列出所有未跟踪或是更改过的文件,相当于`Toggle Git Status Finder`命令
![git status](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_5/git-status.gif)

# 编辑提交信息
你可以通过如下命令将Atom设置为Git的默认编辑器
```
git config --global core.editor "atom --wait"
```
这样当你提交时就会使用Atom来编辑提交信息
并且Atom还支持提交信息的高亮
![git-message](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_5/git-message.gif)

# 状态栏图标
Atom会在窗口右下角显示当前Git的状态,比如当前的分支名,当前文件的状态等
![git-status-bar](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_5/git-status-bar.png)

# 显示当前文件更改情况
Atom会用三种颜色来表示当前文件的更改情况
![git-lines](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_5/git-lines.png)
你还可以通过快捷键`Alt+G ↑`和`Alt+G ↓`来将光标从当前文件的一块更改移到另一块更改

# GitHub支持
如果你的代码托管在GitHub上,掌握下列命令可以让你更方便地工作
* `Alt+G O` 在GitHub上打开当前文件
* `Alt+G B` 在GitHub上用Blame方式打开当前文件
* `Alt+G H` 在GitHub上用History方式打开当前文件
* `Alt+G C` 将当前文件在GitHub上的URL复制到剪切板
* `Alt+G R` 在GitHub上比较分支
![open-on-github](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_5/open-on-github.png)
