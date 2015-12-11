---
layout: post
title: "搭建基于Github Pages和Jekyll的个人博客"
description: ""
category: 
tags: []
---
{% include JB/setup %}

# 搭建基于Github Pages和Jekyll的个人博客

### 安装Git
```
sudo apt-get install git
```
### 安装Jekyll
Jekyll是一个静态网站生成器,非常适合生成博客类的网站
```
sudo apt-get install jekyll rake

```

### 注册[Github](https://github.com/)
* 注册github账号
* 创建一个新的名为`PeterHo.github.com`的repository,请将PeterHo换成你自己的GitHub账号

### 创建博客网站
* 使用现成框架来建立,我选择的是[JekyllBootstrap](http://jekyllbootstrap.com/)
* 上传JekyllBootstrap代码
```language
git clone https://github.com/plusjade/jekyll-bootstrap.git PeterHo.github.com
cd PeterHo.github.com
git remote add origin https://PeterHo@github.com/PeterHo/peterho.github.com.git
git push origin master
```
* 也可以使用Jekyll生成一个全新的网站
```sh
jekyll new site-name
```

### Jekyll使用
* 添加文章
```sh
# 创建文件: ./_posts/2015-12-11-hello-world.md
rake post title="Hello World"
```

* 添加页面
```
# 创建文件 ./about.md
rake page name="about.md"
# 创建文件 ./pages/about.md
rake page name="pages/about.md"
# 创建文件: ./pages/about/index.html
rake page name="pages/about"
```

### 更改博客主题
* 查看现有的[主题](http://themes.jekyllbootstrap.com/)
* 安装主题
```
rake theme:install git="https://github.com/jekyllbootstrap/theme-the-program.git"
```
* 切换主题
```
rake theme:switch name="twitter"
```

### 博客配置
* 配置文件名: `./config.yml`
* 可以在文件中配置各种博客相关的信息
```
title: 博客网站标题
production_url: 主要用于在网站地图等位置显示完整域名
comments: 设置评论
  provider: 选择评论插件,我设置为duoshuo,将其中的short_name项改成自己的名字
```

