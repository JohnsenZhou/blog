---
layout: post
title: Hello Jekyll
data: 2017-04-25
tags: Jekyll
comments: false
---

这个博客通过**Jekyll**搭建，发现刚刚尝试**Jekyll**就被他优美简洁的页面布局以及简单的搭建、发布流程、支持Markdown发布文章给吸引。

##简单的安装方法
就这几个指令：）

```
◆ gem install jekyll bundler
◆ jekyll new my-awesome-site
◆ cd my-awesome-site
◆ bundle exec jekyll serve
Now browse to http://localhost:4000
```

安装完毕后的目录结构通常是这样的：

```
.
├── _config.yml //配置博客的各种基本信息(链接、描述、标题、主题等)
├── _data
|   └── members.yml
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
|   └── 2009-04-26-barcamp-boston-4-roundup.md
├── _sass
|   ├── _base.scss
|   └── _layout.scss
├── _site
├── Gemfile
└── index.html
```

当然你可以到[官方网站](http://jekyllrb.com/)去获取更详细的信息。

对于第一次搭建博客的Coder来说，过程中难免会遇到各种**坑**，这里主要讲讲常见的问题和注意事项：

* **Jekyll**生成后的文件中`_config.yml`中主要是配置博客的各种基本信息(链接、描述、标题、主题等)
* `Gemfile`文件中主要是对依赖的管理，可以在终端中通过
```
gem install '***'
```
来安装依赖。
* `jekyll serve`过后会生成一个叫`_site`的文件夹，这个文件夹也就是之后发布的站点文件。

##部署发布

**Jekyll**完美支持GitHub Pages,一下仅仅根据个人网站做部署建议。

首先你得有一个**Github**账号，[注册一个](https://github.com/)！

* 新建一个**Repository name**为 `用户名.github.io` 例如 `JohnsenZhou.github.io` 项目仓库。
* 将项目bundle后的`_site`文件夹里的文件作为**mater**分支push到远端仓库（这个步骤有待商议，自己在摸索的过程中试过很多发现会报各种bug，这招能够顺利发布）
* 可以在**Git**项目中的Setting选项查看是否构建成功，若成功会有这样的提示：
```
Your site is published at https://johnsenzhou.github.io/
```

****
由于刚刚玩**Jekyll**，后续会陆续完善搭建方案。