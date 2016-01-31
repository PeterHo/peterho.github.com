---
layout: post
title: Atom编辑器入门到精通(二) 插件的安装和管理
date: '2016-01-21 15:26'
---

原创时间:2016-01-21<br>更新时间:2016-01-29

在本节中我们会学习如果安装和使用插件
插件是Atom中一个非常重要的组成部分,很多功能都是以插件形式存在的,比如上篇文章中提到的目录树窗口和设置窗口都是利用默认安装的插件来实现的

# 查看已安装的插件
打开设置窗口(`Ctrl+,`),再切换到"Packages"标签页,你就可以看到已经安装了的插件的列表了
我们可以发现Atom默认安装了70多个插件,Atom通过这些插件提供了各种非常有用的特性和功能
另外在设置窗口的"Themes"标签页中也能看到所有安装过的主题(主题其实也是一种插件)

# 安装插件
在设置窗口中切换到"Install"标签页
在提示有"Search packages"的文本框里输入插件的名字
点"Packages"或者"Themes"来查找安装Atom的插件或主题
![插件安装页面](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_2/packages-install.png)

# 插件设置
当插件安装成功以后也会在上文提到的"Packages"标签页中显示出来
你可以在"Packages"标签页的提示有"Filter packages by name"的文本框中输入插件的名字来搜索已安装的插件
点击插件列表中的"Settings"按钮,就会显示该插件的设置页面.你可以在这个页面中对该插件进行配置和管理
![插件设置](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_2/package-specific-settings.png)

# 主题插件
上文提过主题其实也是一种插件,你同样可以在"Install"标签页中安装主题
![安装主题](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_2/themes.png)
安装完成后就可以使用上篇文章中提到方法来使用该主题了
下图是使用"Unity UI"主题和"Monokai"高亮后的显示效果
![新主题](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_2/unity-theme.png)

# 通过命令行来安装管理插件
当安装好Atom以后你会获得`apm`命令,你可以很方便地在命令终端中通过这个命令来安装管理插件,而不是在界面上点啊点
具体使用方法如下:
* 显示使用帮助

```
# 显示apm命令的使用帮助
# 通过这个命令可以获得apm提供的所有子命令
apm help

# 显示apm命令的install子命令的使用帮助
apm help install
```

* 安装插件

```
# 安装一个插件的最新版本
apm install <package_name>

# 安装一个特定版本的插件
apm install <package_name>@<package_version>

# 比如要安装0.1.5版的Emmet插件
apm install emmet@0.1.5
```

* 搜索插件

```
# 搜索插件名包含coffee的插件
apm search coffee
```
返回结果:
```
Search Results For 'coffee' (29)
├── scallahan-coffee-syntax A coffee inspired theme from the guys over at S.CALLAHAN (35 downloads, 0 stars)
├── coffee-paste Copy/Paste As : Js ➤ Coffee / Coffee ➤ Js (372 downloads, 3 stars)
├── atom-coffee-repl Coffee REPL for Atom Editor (642 downloads, 2 stars)
├── Scoffee-syntax A coffee inspired theme from the guys over at S.CALLAHAN (30 downloads, 0 stars)
├── coffee-navigator Code navigation panel for Coffee Script (2589 downloads, 18 stars)
├── coffee-autocompile Auto compile Coffee-script. (1619 downloads, 3 stars)
├── atom-compile-coffee This Atom.io Package compiles .coffee Files on save to .js files. (myJavascript.coffee -> myJavascript.js) (1666 downloads, 6 stars)
├── coffee-sass-workflow auto-compile onSave of .coffee and .scss files (OSX maybe unix and linux too) (146 downloads, 2 stars)
├── coffee-links a code-links plugin that parses CoffeeScript. (254 downloads, 6 stars)
├── make-coffee Create CoffeeScript version of Javascript files in tree view (263 downloads, 1 star)
├── coffee-porter Convert your JS to Coffescript quickly and flexibly. (325 downloads, 2 stars)
├── coffee-refactor Refactoring support for CoffeeScript (519 downloads, 3 stars)
├── coffee-compile Preview, compile and/or save CoffeeScript in editor to Javascript (16173 downloads, 47 stars)
├── iced-coffee-compiler Quickly compile IcedCoffeeScript code in the editor to JavaScript (88 downloads, 1 star)
├── pen-paper-coffee-syntax A syntax theme specifically for writing papers in markdown. Featuring a paper like color scheme and increased font-size for headings (10210 downloads, 56 stars)
├── CoffeeCompile Auto compile coffee to js on save. (378 downloads, 1 star)
├── coffeescript-build Build the current coffee script file. (1146 downloads, 5 stars)
├── language-typed-coffee-script TypedCoffeeScript language support in Atom (290 downloads, 0 stars)
├── language-coffee-script CoffeeScript language support in Atom (158909 downloads, 25 stars)
├── linter-coffee-variables Lint CoffeeScript for undefined and unused variables (213 downloads, 1 star)
├── language-iced-coffee-script IcedCoffeeScript language support in Atom (361 downloads, 2 stars)
├── language-coffee-script-on-ice IcedCoffeeScript language support in Atom (49 downloads, 0 stars)
├── language-coffee-script-angular CoffeeScript language support in Atom for Angular Developers (2138 downloads, 7 stars)
├── linter-coffeescript Lint CoffeeScript on the fly, using coffee (3391 downloads, 14 stars)
├── language-iced-coffeescript Iced coffeescript for atom (158 downloads, 1 star)
├── language-coffeescript-html CoffeeScript language support with html in Atom (293 downloads, 1 star)
├── js2coffee Convert selected lines or an entire file into coffeescript. (1999 downloads, 11 stars)
├── Coffeefilter Quick and easy coffeescript compilation previews (134 downloads, 1 star)
└── atom-js2coffee A js2coffee plugin for Atom editor (1064 downloads, 0 stars)

Use `apm install` to install them or visit http://atom.io/packages to read more about them.

```

* 显示插件详细信息

```
# 显示git-grep插件的详细信息
apm view git-grep
```
返回结果:
```
git-grep
├── 0.9.0
├── git://github.com/mizchi/atom-git-grep
├── `git grep` in atom editor
├── 3326 downloads
└── 18 stars

Run `apm install git-grep` to install this package.
```
