---
layout: post
title: 搭建基于Github Pages和Jekyll的个人博客
description: ''
category: null
tags: []
---

{% include JB/setup %}

# 安装Git

```sh
sudo apt-get install git
```

# 安装Jekyll
Jekyll是一个静态网站生成器,非常适合生成博客类的网站
- 添加软件源,Ubuntu自带的软件源的Ruby太低

```sh
sudo apt-add-repository ppa:brightbox/ruby-ng
sudo apt-get update222
```

- 安装各种依赖库

```sh
sudo apt-get install ruby2.2 ruby2.2-dev nodejs
```

- 将gem的软件源换成taobao的服务器

```sh
sudo gem sources --remove https://rubygems.org/
sudo gem sources -a https://ruby.taobao.org/
```

- 安装Jekyll和GihubPages

```sh
sudo gem install jekyll
sudo gem install github-pages
```

# 注册[Github](https://github.com/)
- 注册github账号
- 创建一个新的名为`PeterHo.github.com`的repository,请将PeterHo换成你自己的GitHub账号

# 创建博客网站
- 使用现成框架来建立,我选择的是[JekyllBootstrap](http://jekyllbootstrap.com/)
- 上传JekyllBootstrap代码

```sh
git clone https://github.com/plusjade/jekyll-bootstrap.git PeterHo.github.com
cd PeterHo.github.com
git remote add origin https://PeterHo@github.com/PeterHo/peterho.github.com.git
git push origin master
```

- 也可以使用Jekyll生成一个全新的网站

```sh
jekyll new site-name
```

# 代码目录结构
- _layouts 存放模板文件
- _layouts/default.html 博客的默认模板
- _posts 存放博客文章
- index.html 首页文件

# Jekyll使用
- 添加文章

```sh
# 创建文件: ./_posts/2015-12-11-hello-world.md
rake post title="Hello World"
```

- 添加页面

```sh
# 创建文件 ./about.md
rake page name="about.md"
# 创建文件 ./pages/about.md
rake page name="pages/about.md"
# 创建文件: ./pages/about/index.html
rake page name="pages/about"
```

- 本地预览
- # 127.0.0.1:4000
jekyll serve

# 更改博客主题
- 查看现有的[主题](http://themes.jekyllbootstrap.com/)
- 安装主题

```sh
rake theme:install git="https://github.com/jekyllbootstrap/theme-the-program.git"
```

- 切换主题

```sh
rake theme:switch name="twitter"
```

# 博客配置
- 配置文件: `./config.yml`
- 设置Jekyll的Markdown解释器

```
markdown: redcarpet
redcarpet:
  extensions: ["smart", "tables", "no_intra_emphasis", "fenced_code_blocks", "autolink", "strikethrough", "superscript", "with_toc_data", "space_after_headers"]
```

- 设置多说评论系统
- 其中short_name为在多说注册的域名

```
comments :
  provider : duoshuo
  duoshuo :
    short_name : peterho
```

- 其他设置

```
title: 博客网站标题
production_url: 主要用于在网站地图等位置显示完整域名
```

# 绑定域名
- 在项目根目录下新建文件CNAME
- 在文件中添加自己的域名,如`blog.peterho.me`
- 注意只能添加一条域名
- 在DNS解析处新建一条CNAME记录,指向peterho.github.com
- 如果绑定的是顶级域名,则需要新建A记录,ip通过ping peterho.github.com 获得
- 将`_config.yml`中的`production_url`项改为新的域名

# [源代码](https://github.com/PeterHo/peterho.github.com/)
