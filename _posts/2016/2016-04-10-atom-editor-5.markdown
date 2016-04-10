---
layout: post
title: Atom编辑器入门到精通(五) Git支持
date: '2016-04-10 19:38'
---

原创时间:2016-04-10<br>更新时间:2016-04-10

版本控制对于开发来说非常重要,Atom当然也提供了很好的支持,本文将介绍如何在Atom中集成使用Git和GitHub

# 从仓库恢复文件
当你修改了某个文件,然后发现改得不满意,希望恢复文件到最后一次提交的状态,可以使用`Ctrl+Alt+Z`或`Checkout HEAD revision`命令
此命令将会放弃你对文件所有的修改,直接将文件恢复为最后一次提交的版本
相当于Git命令`git checkout HEAD -- filename`和`git reset HEAD -- filename`
![Checkout](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_5/git-checkout-head.gif)
如果恢复文件后发现还是改过以后的好,可以使用`Ctrl+Z`来撤销刚才的修改
