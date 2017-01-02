---
layout: "post"
title: Atom编辑器入门到精通(九) 插件推荐之界面篇
date: "2016-12-10 18:37"
---

原创时间:2016-12-08
更新时间:2016-12-13


# Seti UI
最优秀的UI之一, 包括UI主题和代码样式. 注意它属于themes, 在搜索时如果搜索packages是搜不到的.
```
apm install seti-ui
apm install seti-syntax
```
![seti-ui](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_9/seti-ui.png)

其主要特点是有多种样式主题可以选择和自带了不同文件类型的图标
![seti-ui-colors](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_9/seti-ui-colors.gif)
![seti-ui-icons](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_9/seti-ui-icons.png)


# atom-material-ui & atom-material-syntax
也是一个UI主题+代码样式, 使用了当下最流行的Material风格.
```
apm install atom-material-ui
apm install atom-material-syntax
apm install atom-material-syntax-light
apm install atom-material-syntax-dark
```
他的UI主题同样可以选择多个颜色样式, 然后其代码样式也分为普通黑, 白, 很黑三种.
![material-syntax.png](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_9/material-syntax.png)
![material-syntax-light.png](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_9/material-syntax-light.png)
![material-syntax-dark.png](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_9/material-syntax-dark.png)

我的配置
```
"*":
  "atom-material-ui":
    colors: {}
    fonts: {}
    tabs:
      compactTabs: true
      tintedTabBar: true
    treeView:
      blendTabs: true
      compactList: true
    ui:
      panelContrast: true
      panelShadows: true
```

# File Icons
```
apm install file-icons
```
该插件能在目录树和tab页上根据文件类型显示文件的图标, 使用此插件以后Atom会漂亮很多.
![file-icons](https://raw.githubusercontent.com/PeterHo/images/master/blog/editor/atom/atom_9/file-icons.png)
安装后使用默认设置就好.













https://atom.io/packages/advanced-open-file
https://atom.io/packages/expose
https://atom.io/packages/markdown-folder
https://atom.io/packages/open-recent
https://atom.io/packages/wordcount
https://atom.io/packages/sort-lines
https://atom.io/packages/atom-html-preview
 highlight-selected

linter-swiftc
linter-scss-lint
linter-jsonlint
linter-htmlhint
linter-javac
linter-js-yaml
linter-csslint
linter-jshint
linter-clang
linter-chktex
linter-less
linter-markdown
linter-package-json-validator
linter-shellcheck
git-plus
vim-mode
merge-conflicts
color-picker
 emmet
 # autocomplete-modules
 # auto-update-packages
 # custom-title
 docblockr
https://atom.io/packages/autoclose-html
https://atom.io/packages/dash
https://atom.io/packages/color-picker
https://atom.io/packages/project-manager
https://atom.io/packages/autocomplete-paths
https://atom.io/packages/git-time-machine

minimap

atom-beautify

4、autocomplete-* 系列

autocomplete-*系列包含各个语言的代码自动补全功能，你需要什么语言的就可以下载该语言相关的插件即可。

5、pigments

pigments是项目文件中，样式显色显示的的插件。在Atom中的下载量可是相当的高。对于前端人员来讲还是很重要的一个插件

jshint

js语法检测插件

git-plus

git 操作的插件。目前已经有55万的下载量，使用的人很多，会使用git的同学值得一试。与github深度契合。完美无缺。


    美化
    atom-beautify 一键代码美化
    file-icons 给文件加上好看的图标
    atom-minimap 方便美观的缩略滚动图
    git
    atomatigit 可视化git操作
    代码提示
    emmet 这个不用介绍了吧，前端开发必备，谁用谁知道；
    atom-ternjs js代码提示很强大，高度定制化
    docblockr jsdoc 给js添加注释
    color-picker 取色器 必备插件
    pigments 颜色显示插件 必装
    terminal-panel 直接在atom里面写命令了
    svg-preview svg预览
    便捷操作
    advanced-open-file 快速打开、切换文件
    代码校验
    linter代码校验工具;A Base Linter with Cow Powers
    Web前端
    autoclose-html 闭合html标签
    language-vue-component Atom编写Vue高亮
    vue-autocompile Auto compiles vue in atom
    language-vue Syntax highlighting for vue component files
