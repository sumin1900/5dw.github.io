---
layout:     post
title:      "在Github上免费搭建博客网站"
subtitle:   "使用Jekyll模板搭建、使用Markdown编写，简单，直观"
date:       2017-10-31 21:00:00
author:     "5dw"
header-img: "img/blog.jpg"
header-mask: 0.3
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
`git`命令可以用来管理github上的repository，可以把内容下载到本地，也可以把本地的修改上传到github。当然还可以做很多版本管理的事情，这里不涉及，有兴趣的可以自行搜索学习。在我们搭建博客网站的过程中主要需要用到下面几条命令：
1. `git clone`: 可以把github上的一个repository下载到本地,而且它会把这个本地目录和你的github repository对应关系记录下来.
    * 我们用`git clone https://github.com/5dw/5dw.github.io.git 5dw`来把repository下载到本地。这里当然你需要把5dw换成你自己的名字。面最后一个5dw是本地目录的名字，你可以指定不同的目录名，也可以省略，那样git会帮你建一个叫做5dw.github.io的目录。
    * 你打开新建的本地目录会发现里面有两个东西。一个叫`.git`，另一个叫`README.md`。第一个是个目录，用来存放git自己所需要的信息，比如和github repository的对应关系，本地修改历史等等。因为前面的那个小点，所有在某些系统里可能是隐藏的。能不能看到它都没关系，因为你不需要手动对它做任何事情。而README.md这个文件是一个说明文件，当你在github里打开你的repository首页的时候，会显示这里面的内容。格式是markdown。但是因为咱们这里的目的是搭建博客网站，我们的读者不会直接到github里去看repository，所以README.md的内容也没关系。
2. `git stage`: 和`git add`完全一样。把本地的修改打包（暂且用这个词），告诉git我接下来会把哪些本地修改提交上去。
    * `git stage 2017*.md`，这条命令会把所有以2017开头的.md文件打包。
    * `git stage *`，这条会把本地在上次提交之后的所有修改打包。
3. `git commit`：把已经打包的修改提交到本地repository。
	* `git commit -m "description"`，你需要在提交的时候填写description来说明你这次提交的内容是关于什么的修改。这个说明信息是必须的。
4. `git push`：把本地提交的修改上传到服务器，也就是github。
5. `git pull`：把服务器上的最新版本下载到本地。
6. 使用`git push`和`git pull`的时候需要注意，如果你在不同的机器上编辑同一个repository，比如多个人协同编辑，需要保证尽量避免冲突。在有冲突的情况下这两条命令会要求你解决这些冲突，比如保留哪一份提交等等。

# 选择现成模板
Jekyll很不错，但是我不想自己从0开始设计自己的网站样式。所以我选择直接应用现成的模板。有很多好心人自己做了模板拿出来和大家分享，本站用的就是[Hux](http://huangxuan.me/)的模板。你也可以到[jekyllthemes](http://jekyllthemes.org)等网站上找自己喜欢的模板。你也可以把本站做为自己的模板，但请注明来自Hux。

当你选中一个模板之后，就需要把它下载到本地，并做些修改。方法就是用上面的git命令，因为这些模板也都是存在github中的。

以Hux的模板为例。我通过命令`git clone https://github.com/Huxpro/huxpro.github.io.git hux`就把整个模板下载到了本地一个叫hux的目录中。如果你是用的Windows系统，而且没有安装Jekyll也自然没有创建自己的first网站，那么这个hux目录就可以被看作是你新建的网站，只不过你是站在了别人的肩膀上。这个hux目录和前面的first目录在下面的步骤中可以一样对待。

## 模板格式
打开已经下载的模板目录，你会发现里面有如下内容（不同的模板可能有所有同，但原理类似，这里只解释主要的几个）：

1. index.html：网站主页。
2. _config.yml：网站全局配置文件。
3. 404.html：当用户访问到不存在的网页的时候会显示这个页面。
4. .git目录：git的目录，**不要动**！
5. _layouts目录：存放布局模板的地方。
6. _posts目录：存放所有博客文章的地方。当网站完成搭建后，主要的工作就是往这里面添加新文章。网站会自动更新。
7. _includes目录：模板需要用到的其它内容。在Hux的博客中这里面是一些通用的网页部分，比如页头页脚，导航条等。
8. README.md：github repository的说明文档。这里可以空着，也可以写一些你自己的内容。只要不保留你所用模板的README就行，否则找开你的repository看到的是别人的repository的说明。
9. LICENSE：你的整个repository的许可。这里指的是软件许可，有些是允许别人随意使用你创造出来的内容，也有些可以限制别人对你内容的使用。本站继承了Hux的Apache许可。

### _config.yml格式
这是整个网站中最重要的一个配置文件，ymal格式（如果需要了解更多，请自行搜索），里面包含了你的网站需要用到的一些配置。如果你使用的是别人的模板，在上传之前一定要修改！

所有的配置项都是以`<配置名>:<配置值>`这样的键值对写在里面的。`#`开关的内容直到此行结束会被看做是注释。

比如`title: 五D网`，就是有一个配置项的名字是`title`，而它的值是`五D网`，在其他的地方当你需要引用这个配置的时候就直接写`{{site.title}}`，网站会把它直接替换成你所配置的值，这里就会是`五D网`。

你也可以随意增加自己配置项，但需要确保名字不要重复，而且确实有必要。

### html模板格式
Jekyll中的html文件都是用做页面模板的，里面是HTML语言+Jekyll模板语言构成的。

Jekyll模板语言中有两类需要解释：
1. 逻辑语句，用`{% raw %}{% xxx %}{% endraw %}`来表示。常用的有if条件语句，for循环等。
2. 配置内容，用`{% raw %}{{ xxx }}{% endraw %}`来表示。常用的就是显示配置项的值。

比如：
```
{% raw %}
{% if page.author %}
    {{ page.author }}
{% else %}
    {{ site.title }}
{% endif %}
{% endraw %}
```
意思是如果当前显示的page中定义了author配置项，则显示其内容，否则就显示_config.yml中的title配置项的内容。

```
{% raw %}
{% for post in paginator.posts %}
<div>
    <a href="{{ post.url | prepend: site.baseurl }}">
        {{ post.title }}
    </a>
</div>
{% endfor %}
{% endraw %}
```

意思是遍历所有的post，并且显示链接到这些post页面，链接的内容是post中配置的title。如果你有十个博客文章，这里就会显示十个链接，分别链接到那十个博客文章的页面。

> * 上面的page.author，是页面的配置项，写在页面开头的yaml里面。比如在index.html或about.html等里面，或者在_posts里面的博客文章里。
> * _config.yml之外的ymal配置项，在我们的网站中就是某些文件开头被`---`包围起来的内容。格式和上面说的_config.yml一样。
> * 比如：
> 
> ```
> ---
> author: 5dw
> ---
> 
> 其它内容……
> ```
> 
> * 页面或博客文章中有一个配置项是`layout`，这个决定了这个页面的内容会被用哪个格式文件显示。比如一个文章的layout设置成了post，也就是`layout: post`，而我们在_layout下面有个post.html格式文件，那么当你需要访问这个文章的时候，网站会把post.html载入，并把这个文章中的所有内容替换post.html中的`{% raw %}{{content}}{% endraw %}`。当然，post.html也可以设置layout，把它嵌套进另一个格式文件。

## 本站对模板所做的修改
借来了Hux的模板，为了满足自己的要求做了一些修改：
1. 删除了除主页之外的其他页面（除了404）。并修改了_includes/nav.html，注释掉了导航菜单。
2. _includes/footer.html中之前在页面最下面显示linkedin, github, facebook等的图标链接，增加了邮件图标。根据`site.email`来显示。
3. 修改了一些hardcode的内容。比如页面上的`ABOUT ME`, `FEATURED TAGS`等等。在_config.yml中添加了相应的配置，并用这些配置替换模板中的hardcode内容。这样可以方便对这些内容做修改（万一我想修改）。
4. Disqus评论之前全局控制的，如果_config.yml中设置了Disqus用户名，那么所有的博客文章页面下面都会显示评论框。本站增加了博客文章中的comment配置，只有当_config.yml中设置了Disqus用户名，并且一个博客文章中comment配置值为true的时候，这个博客的页面才会显示评论框。这样可以部分开启评论。
5. catalog可以在一个博客文章页面开启，但是Hux Blog里也有文章开启了，但却没有目录出现，原因是还需要这个页面中有multilingual这个配置，不管它是true还是false，否则的话目录就没办法生成。本站在所有的博客文章中都增加了multilingual配置。（Hux的这个配置原本的意思是要控制一篇文章是不是有中文和英文两个版本，如果有就按选择的语言显示。)



## 注意事项
1. CNAME文件。如果有这个文件，一定要把内容修改成自己的域名，否则会出错。
2. README.md。如果是借用的别人的模板，一定要修改。
3. package.json。这里面是一些用于打包应用的信息，虽然博客网站不会直接使用到它，但如果你是借用的别人的模板，也一定要把里面的内容做相应的修改。
4. 邮件提醒。我们把网站内容修改后上传到github，但有时候打开网站页面变没有改变。这时候就有可能是我们的网站中有错误，可以先查看自己邮件，因为github在build失败后会给我们发邮件提醒。邮件里会有一些线索找到哪里出了问题。
5. 转义。如上文中，我们需要在博客文章中显示`{% raw %}{% xxx %}{% endraw %}`之类的模板语句，但如果直接客以写网站会试图翻译它们，这不是我们想要的。所以我们需要把它们转义。方法就是在两边用`{% raw %}{% ra{% endraw %}{% raw %}w %}{% endraw %}`和`{% raw %}{% endra{% endraw %}{% raw %}w %}{% endraw %}`包裹起来。

# 满意上传

现在我们有了本地jekyll的一个虽然丑陋但完整的博客网站或者是“剽窃”的别人的模板并做了相应修改，也有了github repository，也知道了git命令的用法。下面我们把这些连起来用，把我们的本地网站上传到github看一下效果。
1. 找到上面你创建的jekyll网站目录（我用的是first）或者是下载的现成的模板目录（我用的是hux目录），把里面所有的内容复制，并粘贴到`git clone`下载的repository本地目录中。需要注意的是，如果你是从别人的模板中复制内容，你**一定不要**把他的.git目录一起复制，因为那样你的repository信息就会丢失，而被别人的repository信息替换，而你又没有对别人的repository的写权限，所以后面上传的时候会出问题。
2. 从命令行进入到你的本地repository目录。
3. `git stage *`
4. `git commit -m "my first upload"`
5. `git push`。有可能需要你输入你的github用户名和密码。

如果没有报错，完成上面步骤之后，你的本地内容已经成功上传到了github中。现在你的博客网站已经上线，可以去查看一下。从浏览器中打开地址http://5dw.github.io，当然你还是需要把这里的5dw替换成你自己的github名字。

> 恭喜你有了自己的博客网站，是时候开始写作影响世界了！！

# 开始写作之旅，添加自己的博客文章

有了自己的博客网站，剩下的事情就是写文章了。我们需要做的事情只有一件，就是在_posts下面不停地添加markdown文件，每一个文件对应一个文章。每个文章有如下格式：
> ---
> XXX1: YYY2
> XXX2: YYY2
> ---
> 
> Markdown内容

开头是ymal配置信息，一般会有title，date等等，这取决于你的模板文件中都用到了哪些。需要特别注意的是date这个东西，需要严格按照格式`2017-02-09 12:00:00`来。

Markdown内容就是你的文章正文，Markdown的说法可以自行搜索。

顺便打个广告，当我在Windows 10上写作的时候，我用Bookpad app，可以在[Store](https://www.microsoft.com/store/apps/9N6P5ZH2SJSX)里面找到。界面如下：
![](/img/bookpad.png)

