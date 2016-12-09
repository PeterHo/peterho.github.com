---
layout: post
title: Atom编辑器入门到精通(七) 编辑配置文件
date: '2016-10-16 11:13'
---

原创时间:2016-10-16
更新时间:2016-12-09

在之前的章节中我们已经知道Atom给我们提供了基于图形界面的配置方式. 对于初学者, 这种配置方式无疑是很方便的. 其实我们还能通过直接编辑配置文件的方式来更灵活地配置Atom. 下面我们就来学习配置文件的使用方法.

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

# 样式微调
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


# 配置热键
在Atom中热键的配置方式与主题类似, 举个例子:
```
'atom-text-editor':
  'enter': 'editor:newline'

'atom-text-editor[mini] input':
  'enter': 'core:confirm'
```
上面的代码定义了`Enter`键在不同环境中的不同表现. 在正常的编辑窗口中按`enter`键触发`editor:newline`命令, 也即是普通的回车. 而当在一个编辑框中键入`enter`时, 则会触发`core:confirm`命令.

在默认情况下, 当Atom启动时会加载`keymap.cson`文件来获取自定义热键, 并且`keymap.cson`是最后被加载的配置文件, 这样可以保证我们配置的热键可以覆盖Atom自身或其插件定义的热键. 这个文件同样位于`~/.atom`目录下, 当然也可以通过主菜单`Edit`->`Keymap...`来直接编辑这个文件.

我们也可以在设置窗口的`Keybindings`页面查看当前所有的快捷键.

Atom还提供了一个窗口来帮助我们调试热键的设置, 可以使用`Ctrl+.`或命令`Key Binding Resolver: Toggle`来呼出该窗口. 此窗口可以实时显示我们按下的热键所对应的处理方法.

# 全局设置
Atom的主配置文件为`~/.atom/config.cson`, 可以通过菜单`Edit`->`Config...`或命令`Application: Open Your Config`来打开此文件.
这个文件是长这个样子的:
```
"*":
  core:
    themes: [
      "atom-material-ui"
      "atom-material-syntax"
    ]
  editor:
    tabLength: 4
".json.source":
  editor:
    tabLength: 4
```

其中以`"*"`为根的配置信息是面向全局的, 而类似于`".json.source"`或`".python.source"`为根的配置是面向特定语言的.

具体的全局配置项请参考[官方文档](http://flight-manual.atom.io/using-atom/sections/basic-customization/#configuration-key-reference)

# 面向特定语言的设置
上一节中我们已经知道除了配置全局项, 我们还可以通过编辑`config.cson`针对特定的语言来进行相应的设置.
比如我们需要Markdown文件使用自动换行, 而ruby文件的tab长度为2, 但python文件的tab长度又为4, 就可以这样设置:
```
'*': # 其他语言
  'editor':
    'softWrap': false
    'tabLength': 8

'.source.gfm': # markdown
  'editor':
    'softWrap': true

'.source.ruby': # ruby
  'editor':
    'tabLength': 2

'.source.python': # python
  'editor':
    'tabLength': 4
```

常见的配置项有
```
editor.autoIndent
editor.autoIndentOnPaste
editor.invisibles
editor.nonWordCharacters
editor.preferredLineLength
editor.scrollPastEnd
editor.showIndentGuide
editor.showInvisibles
editor.softWrap
editor.softWrapAtPreferredLineLength
editor.softWrapHangingIndent
editor.tabLength
```

至于如何获得指定语言的文件类型名字, 在我们教程的第四章中已经讲过了, 也就是通过`Settings`窗口的`Packages`中搜索到需要配置的语言, 就可以在Scope项处看到该语言的文件类型名了, 如下图:
![python-grammar](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_7/python-grammar.png)
同时我们也可以在这里对该语言进行一些图形化的设置:
![python-settings](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_7/python-settings.png)

另外还有一种更简单的获取名字的方法: 先将光标置于目标文件, 再键入`Ctrl+Alt+Shift+P`, Atom会显示当前光标处的某些信息, 其中第一条一般就是该文件的类型名字, 这些信息在以后学习自定义主题样式的时候也用得着.
![cursor-scope.png](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_7/cursor-scope.png)

# 自定义语言
假如我想Atom将扩展名为`foo`的文件识别为CoffeeScript, 那么可以在`config.cson`文件中这样设置:
```
'*':
  core:
    customFileTypes:
      'source.coffee': [
        'foo'
      ]
```
