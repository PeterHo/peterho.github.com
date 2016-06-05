---
layout: post
title: Atom编辑器入门到精通(三) 文本编辑基础
date: '2016-01-29 10:29'
---

原创时间:2016-01-29<br>更新时间:2016-06-05


身为编辑器,文本编辑的功能自然是放在第一位的,此节将总结常用的文本编辑的方法和技巧,掌握这些技巧以后可以极大地提高文本编辑的效率

注意此节中用到的快捷键是Mac下的,如果你用的系统是Win或者Linux,可能会有一点不同.

# 光标移动
在编辑文本的过程中移动光标是一种频率很高的操作.
我们不应只满足于通过鼠标或键盘的方向键的这种效率很低的操作方式来移动光标,让我们来看看还有哪些能极大提高编辑效率的方法吧

## 光标上下移动
* 光标移动到上一行: `Ctrl+P` 或 `Up`
* 光标移动到下一行: `Ctrl+N` 或 `Down`
* 光标移动到文件头: `Cmd+Up`
* 光标移动到文件尾: `Cmd+Down`

## 光标左右移动
* 光标向左移动一个字符: `Ctrl+B` 或 `Left`
* 光标向右移动一个字符: `Ctrl+F` 或 `Right`
* 光标向左移动一个单词: `Alt+B` 或 `Alt+Left`
* 光标向右移动一个单词: `Alt+F` 或 `Alt+Right`
* 光标移动到行头: `Ctrl+A` 或 `Cmd+Left`
* 光标移动到行尾: `Ctrl+E` 或 `Cmd+Right`

## 移动到指定行/列
通过快捷键`Ctrl+G`来呼出光标移动窗口,填入`行:列`后回车就可以将光标移动到指定位置
![定点移动](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_3/goto.png)

## 符号间跳转
这里的符号是指`Symbols`,包括代码中的函数名,变量名等
在当前文档搜索并跳到符号: `Cmd+R`
在工程内搜索并跳到符号: `Cmd+Shift+R`
![符号间跳转](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_3/symbol.png)
`Cmd+Shift+R`需要需要`tags`文件的支持,如果你以前使用过Vim等编辑器应该对这个机制很熟悉了

## 使用书签
* `Cmd+F2`: 在当前行创建或取消书签
* `Ctrl+F2`: 列出所有书签
* `F2`: 跳转到下一个书签
* `Shift+F2`: 跳转到上一个书签

# 选择
在Atom中,如果你希望在移动光标的时候顺便选中内容,只需要在移动快捷键中加上`Shift`.

## 上下选择
* 向上选择一行: `Ctrl+Shift+P` 或 `Shift+Up`
* 向下选择一行: `Ctrl+Shift+N` 或 `Shift+Down`
* 选择当前位置到文件头: `Cmd+Shift+Up`
* 选择当前位置到文件尾: `Cmd+Shift+Down`

## 左右选择
* 向左选择一个字符: `Ctrl+Shift+B` 或 `Shift+Left`
* 向右选择一个字符: `Ctrl+Shift+F` 或 `Shift+Right`
* 向左选择一个单词: `Alt+Shift+B` 或 `Alt+Shift+Left`
* 向右选择一个单词: `Alt+Shift+F` 或 `Alt+Shift+Right`
* 向左选择到行头: `Ctrl+Shift+A` 或 `Cmd+Shift+Left`
* 向右选择到行尾: `Ctrl+Shift+E` 或 `Cmd+Shift+Right`

## 其他选择
* `Cmd+L`: 选中当前行
* `Cmd+A`: 全选
* `Ctrl+Shift+W`: 选择当前单词


# 文本编辑与删除
## 基本操作
* `Ctrl+T`: 相互调换光标前后字符
* `Cmd+J`: 将下一行接到当前行尾
* `Ctrl+Cmd+Up`/`Ctrl+Cmd+Down`: 将当前行向上/下移动一行
* `Cmd+Shift+D`: 复制当前行
* `Cmd+K, Cmd+U`: 连续输入两个快捷键,将当前单词转为大写字母
* `Cmd+K, Cmd+L`: 连续输入两个快捷键,将当前单词转为小写字母
* `Cmd+Alt+Q`: 段落重排(在英文写作时比较有用)

## 删除和剪切
* `Ctrl+Shift+K`: 删除当前行
* `Cmd+Backspace`: 从当前光标删除到行头
* `Cmd+Delete`: 从当前光标删除到行尾
* `Alt+Backspace`/`Alt+H`: 从当前位置删除到单词头
* `Alt+Delete``Alt+D`: 从当前位置删除到单词尾

## 多光标选择
多光标选择是SublimeText的特色功能,现在Atom也能支持了,具体的使用方法如下:
* 添加一个新的光标: 按住`Cmd`键后用鼠标点击或选择想要添加新光标的位置
* `Cmd+Shift+L`: 将选中的多行转成多光标的形式
* `Cmd+D`: 选中下一个与当前光标所在单词相同的单词(或是与当前选中单词相同的单词)
* `Ctrl+Cmd+G`: 选中所有与当前光标所在单词相同的单词(或是与当前选中单词相同的单词)

![多光标](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_3/multiple-cursors.gif)
通过多光标选择能够很方便地同时编辑多处代码

## 括号和引号
Atom对括号和引号有很多的支持,其中包括:
当光标位于括号(包括{}[]())上时,会高亮其对应的另一半括号.同样的,Atom也支持高亮XML和HTML的标签
自动补全括号{},[],(),引号",',\`
选中一段文本,然后输入括号或引号,会自动在选中的文本两端添加括号或引号
使用`Ctrl+M`可以让光标跳转到临近的括号处,再按一次快捷键光标会跳到另一个对应的括号处
使用`Ctrl+Cmd+M`可以选中当前括号内所有内容
使用`Cmd+Alt+.`可以补全XML/HTML的标签,比如说当输入`<body>`后再键入`Cmd+Alt+.`会自动添加`</body>`

## 文件编码
当你打开一个文本文件时,Atom会自动判断文件的编码方式,如果不能识别就会默认使用UTF-8
你可以使用`Ctrl+Shift+U`来呼出编码选择窗口并手动选择文件的编码方式
![文件编码](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_3/encodings.png)

# 查找和替换
Atom的查找使用方式与大部分编辑器一样
使用`Cmd+F`进行文件内查找
![查找和替换](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_3/find-replace-file.png)
使用`Cmd+Shift+F`进行工程内查找
![工程内查找](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_3/find-replace-project.png)
在查找窗口中输入需要查找的文本后可以使用回车或`Cmd+G`跳到下一个查找的结果
在查找窗口中中还可以对使用正则表达式,大小写敏感,查找选中块,查找整个单词等选项进行设置
在多文件查找时你还可以通过在`File/directory pattern`文本框中输入通配符来限定只查询某一些文件
