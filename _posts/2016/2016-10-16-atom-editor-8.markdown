---
layout: post
title: Atom编辑器入门到精通(七) Markdown支持 (下)
date: '2016-12-08 20:24'
---

原创时间:2016-12-08
更新时间:2016-12-08

在上一章中我们了解了原生Atom对Markdown的支持, 这一讲我们一起学习如何通过更多的插件让Atom更好地支持Markdown文件.

# Markdown-Writer
如果你跟我一样, 使用Markdown格式来写博客, 那你一定也需要Markdown-Writer插件, 它能让更方便地管理和编辑Markdown文件.
安装
```
apm install markdown-writer
```


# CSON
CSON(CoffeeScript Object Notation)是Atom配置文件的文件格式, 它使用键值对的格式来存储数据. 就像下面这个样子
```
key:
    key: value
    key: value
    key: [value, value]
```
跟Python类似, CSON使用缩进来标识语句块.

CSON的key的名字不能重复, 如果CSON中包含了多个同名的key, 那么最后的那个key的值会覆盖之前同名的key.
因此**不能**这样配置
```
# 只有第二个snippet会被载入
'.source.js':
  'console.log':
    'prefix': 'log'
    'body': 'console.log(${1:"crash"});$2'
'.source.js':
  'console.error':
    'prefix': 'error'
    'body': 'console.error(${1:"crash"});$2'

```
而应该这样配置
```
# 两个snippets都会被载入
'.source.js':
  'console.log':
    'prefix': 'log'
    'body': 'console.log(${1:"crash"});$2'
  'console.error':
    'prefix': 'error'
    'body': 'console.error(${1:"crash"});$2'

```

value可以是字符串, 数字, 对象, 布尔值, null, 或数组.

# 主题微调
有这样一个场景, 我们想对一个主题中的某个元素的style进行一点点修改, 但又不想(或是不会)创建一个完整的主题包, 这个时候我们就可以通过编辑`styles.less`文件来达到目的. 这个文件位于`~/.atom`目录下, 是一个Less语言(一个CSS的预处理程序)的源文件.
我们可以使用Atom来打开并编辑这个文件, 也可以通过主菜单`Edit`->`Stylesheet`来更方便地打开它.

举个例子, 如果我们想要改变状态栏的颜色, 可以在`styles.less`中加入
```
.status-bar {
  color: white;
  background-color: black;
}
```
就这么简单.

但我们如何知道需要修改的对象的类名和属性名呢. 我们知道, Atom是基于Node.js和Chromium开发的, 那么我们当然也可以使用Chromium提供的开发工具来调试它. 呼出开发工具的快捷键为`Ctrl+Shift+I`.
![devtools](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_7/devtools.png)
我们可以使用开发工具来检索Atom中所有的元素. 如果需要修改某个元素的style, 在上文中提到的`styles.less`中修改其属性值即可. 如果你不会Less, 那就把它当作CSS吧.

## 调整编辑区的样式
Atom的为了将编辑区的样式与其他部分隔开, 使用了一个Shadow DOM.
因此, 如果我们想要调整编辑区的样式, 需要用`atom-text-editor::shadow`选择器来标识它.
举个例子, 如果你想改变光标的颜色, 只使用`.cursor`选择器是不够的, 还的在它前面加上`atom-text-editor::shadow`.
```
atom-text-editor::shadow .cursor {
  border-color: pink;
}
```

# 配置热键
在Atom中热键的配置方式与主题类似, 举个例子:
```00000000000000000000000000000.......................00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
'atom-text-editor':
  'enter': 'editor:newline'

'atom-text-editor[mini] input':
  'enter': 'core:confirm'
```
上面的代码定义了`Enter`键在不同环境中的不同表现. 在正常的编辑窗口中按`enter`键触发`editor:newline`命令, 也即是普通的回车. 而当在一个编辑框中键入`enter`时, 则会触发`core:confirm`命令.

在默认情况下, 当Atom启动时会加载`keymap.cson`文件来获取自定义热键, 并且`keymap.cson`是最后被加载的配置文件, 这样可以保证我们配置的热键可以覆盖Atom自身或其插件定义的热键. 这个文件同样位于`~/.atom`目录下, 当然也可以通过主菜单`Edit`->`Keymap...`来直接编辑这个文件.
































a
