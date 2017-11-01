---
layout:     post
title:      "在Github上免费搭建博客网站"
subtitle:   "使用Jekyll模板搭建、使用Markdown编写，简单，直观"
date:       2017-10-31 21:00:00
author:     "5dw"
header-img: "img/blog.jpg"
header-mask: 0.0
catalog:    true
comment: true
multilingual: false
tags:
    - 博客
    - Blog
    - Github
    - Jekyll
    - Markdown
---

> * 在Github里面我们可以存储和管理代码，同样也可以存储和管理文章。
> * Github的Pages功能出来之后使我们可以用存储在其上的内容来构建自己的网站。
> * Jekyll是一个可以把**静态**内容转成博客网站的工具，它是免费的。
> * Github Pages支持Jekyll，所以我们可以使用Jekyll更轻松地搭建自己的博客网站，而且Github支持自定义域名。
> * 我们可以使用Markdown语言来写文章，在Github Pages上展示。
> * Github帮助我们存储和管理文章，Jekyll帮助我们本地调试网站。


本网站就是用这种方法搭建而成的，你可以通过探索本站了解到这种方式可以达到的效果。

# Jekyll安装和尝试
> Jekyll不是必须的。但是它可以在本地启动一个服务器让你不需要上传内容就可以看到效果，从而帮助你调试网站，直到满意，才把内容上传到Github上去。这可以节省不少的时间。

## 下载和安装Jekyll
你可以从Jekyll的网站([英文](http://jekyll.com/)或[中文](http://jekyll.com.cn/))上得到所有需要的信息。这里简单介绍一下必须的步骤。
1. 官方不建议在Windows下安装Jekyll，虽然你可以做到。这里建议，如果你用的是Windows系统，那么你可以跳过Jekyll部分，因为没有它你一样可以成功搭建你的网站，只不过不能本地调试而已。这里以**Macbook**为例（Linux类似，Windows请绕行）。
2. 通过命令`gem install jekyll`来安装jekyll
3. 通过命令`jekyll new first`来创建自己的本地网站。这里‘first’是网站名，也是本地目录的名字，你可以随便用任何你想用的名字。
4. `cd first`进入网站目录
5. `jekyll serve`来启动本地服务，如下图所示：
![](/img/jekyll_first.png)
6. 之后你便可以用任何浏览器访问`http://localhost:4000`或`http://127.0.0.1:4000`，这就是你的博客网站了，就这么简单！！
![](/img/jekyll_site.png)

显然，这个博客网站不够完美，但是它确实已经是一个完整的博客网站，你可以把它部署到Github上看一下效果。你当然也可以完成以下的所有步骤之后再上传。

# Github注册
如果你的内容是可以公开的，允许任何人查看，那么Github对你来说是免费的。但如果你希望自己的内容是私有的，那么你需要付费。这里我们以免费的内容为例。如果你还没有Github账号，那么你需要注册一个。
1. 在[Github网站](https://github.com/)上点右上角的注册(Sign Up)按钮按照提示完成注册。
![](/img/github_reg1.png)
2. 新建一个repository。这里需要注意，这个新的repository的名字**必须**是`[你的名字].github.io`。比如本站的github名字是5dw，那么对应的repository就是`5dw.github.io`.
![](/img/github_reg2.png)

# Git用法
# 选择现成模板
# 一般问题
