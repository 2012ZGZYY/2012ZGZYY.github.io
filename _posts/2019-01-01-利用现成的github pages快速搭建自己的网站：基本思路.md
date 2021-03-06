---
layout: post
title:  "新年的第一篇博客：利用现成的github pages快速搭建自己的网站：基本思路"
category: website
date:   2019-01-01 13:00:00
comments: true
categories: Personal

---  

第一篇博客写写这个个人主页的搭建过程吧。关于如何利用github pages以及[jekyll](https://www.jekyll.com.cn/)之类的开源框架来快速搭建自己的个人主页在网络上已经有很多很好的教程了，我这里就不重复这种文章了。但在各式琳琅满目的教程中，往往只手把手教你怎么做，却很少告诉你为什么这么做，这不得不说是种遗憾。显然技术细节永远是次要的，重要的是其中基本的观念和思想。所以在这篇博文中，我只说说搭建主页过程中的基本概念和思路。我会尽量只采用文字介绍，不使用配图，免得文章篇幅太长而抓不住重点。  

做网页所需的前端技术已经不是什么新鲜事了，不过是用到html+css+JS从而把图片和文字以一种规则性的方式呈现出来。jekyll做好了一套这样的东西，相当于是提供了一个模板。所以它本质上是一个文本转换引擎：你负责用喜欢的标记语言来写文档，它负责帮你生成一个花哨的网页。而github免费给你提供了一个username.github.io的域名，可以让你把自己的主页呈现到网络上。你需要做的就是把这套网页所需的html等文件放到你的github远端仓库中就好了，github pages会自动利用jekyll生成网站。  

因为前人已经做好了很多好用的主页，所以你可以选择做个伸手党，直接把别人的东西改改就可以用了。按如下步骤：

1.找到一个别人做好的github.io项目，比如[笔者的个人主页](http://github.com/2012ZGZYY/2012ZGZYY.github.io/)。可以看到我的这个项目下已经有了现成的搭建主页所需的所有文件。

2.当你把别人的项目fork到你自己的github远端仓库中（为了尽可能不对原项目造成干扰，建议采用clone而非fork的方式），此时在你自己的github主页下会多出这个项目及其项目文件，但此时其仓库名称还是别人的。为此，你需要把它改成你自己的，只要这样，github才能识别这是你的主页。修改名称在settings中修改。这样，这个主页项目就变成你的了，你可以在浏览器中输入域名：username.github.io，此时展现出的网页就是这个项目设计的主页。

  *评注：以上两步实际上已经完成了整个个人主页的搭建，大概只需几分钟。其实github本身也提供了一些网页主题，如果你不想fork别人搭好的东西，你也可以先创建一个名为username.github.io的空仓库，然后在github-Settings-GitHub Pages-choose a theme中自己选择即可。*

3.后续工作是把别人网站文件中涉及到的个人信息改成你自己的，这涉及到一些前端知识，但也很简单。无非就是修改全局参数文件_config.yml中的一些参数，以及所有涉及到个人信息的.html文件中的一些参数。这一步的目的就是将网站主页上显示的一些用户名、时间、格言、题目等等按照你自己的想法统统换掉，从而完完全全地抹去上一个用户的信息，变成你自己的。这些修改可以完全在github网站上进行，也可以先将整个项目拉取到你自己的本地电脑上，然后在本地修改完后再推送到远端去。

  *评注：至此，你已经完完全全搭建好了一个属于你自己的个人主页。显然，你最初的目的肯定是希望能在这个网页上写点自己的博客。所以接下来的问题是如何使用它了。跟第3步一样，你既可以选择直接在github网站上直接进行网页操纵：创建新文件，写博客，提交；也可以将项目拉取到本地之后在本地创建新博客然后推到远端。出于方便一般还是采用后者。这些操作涉及到简单的git和github知识。*

4.将项目拉取到本地（个人电脑）后，切换到_posts文件夹下。在这里存放的就是你的博客文件。这些文件必须遵循一定的命名规则和写作规则，否则不能被你的网页正确识别。这些规则包括: 文件名采用2019-01-01-My blog name.md的方式，即时间+标题的形式，空格用-连接表示。文件后缀.md表示这是markdown文件，也就是必须使用markdown这种轻量级的标记语言来编辑。所以你需要下载一个markdown文件的编辑器，这东西很简单，半个小时就能学会。在每篇文章中，你需要在头部加上yaml头信息：即使用两条三虚线包含一些信息。这样它们才能从源格式被转换为html页面。

5.其他操作。为了自定义更骚包的个人主页，你还可以进行很多别的复杂操作。你可以在现有项目的基础上进行修改，从而改变网页布局。这需要你具备足够的前端知识，主要是熟悉html文件。比如，你可以添加评论系统，网站统计等。关于这部分操作，你可以查看[jekll的开发文档](https://www.jekyll.com.cn/)。你也可能觉得github提供的域名不够个性化或不够方便，毕竟github禁止了百度爬虫，所以你在百度上是搜不到github.io域名的。为此你可以自己购买一个域名并链接到你的主页上去，从而让别人能在百度上搜到你的网站。

**总结起来**，为了利用github pages搭建一个个人主页，你大概需要掌握如下知识点：  
1.基本的git和github原理及操作方法（可采用命令行操作，也可使用github desktop图形界面）。这使你可以建立一个从本地仓库到远端仓库的链接，从而上传本地文档到远端网站（虽然你也可直接在远端创建）。如果采用命令行操作git，为了避免每次push的时候输入密码，你可能需要配置下ssh keys到github，这也是为什么有的教程里莫名其妙地写一段这个的原因。但实际上这个是无关紧要的东西。  
2.前端知识，大概了解开源框架jekyll的结构。这使你明白应该如何修改编辑.html等文件并按自己的需求进行设计修改。如果你想要通过修改jekyll来自定义网站，那么你需要更深入地学习jekyll本身。比如，你很可能有必要在本地安装jekyll，只有这样你才能方便地在本地预览网页。这也是为什么有的教程里介绍了怎么安装配置jekyll，尽管这对于搭建站点而言并非必须的。    
3.懂得如何使用markdown方式进行文档编辑。这是你写博客的方式。  
4.基本的网络知识。这使你可以购买和配置自己的网站域名，使得别人能更容易地访问到你的主页。这也是为什么很多教程讲了自己购买、配置域名并将站点提交到百度谷歌的方法，虽然对于搭建个人网站本身而言这不是必须的。  

关于jekyll（两大静态博客主流框架jekyll和hexo之一）：
1.文件结构
_config.yml：保存配置（jekyll会自动加载这些配置）
_includes文件夹：存放可重复利用的文件，可被其他文件包含（{%include文件名%}），常用于在各个模板中复用如导航条、标签栏、侧边栏之类在每个页面上都一样的内容
_layouts文件夹：存放模板文件（标签{{content}}将content插入页面中）
assets：没特殊要求，主要用于存放资源文件如图片、样式表、脚本等
_posts文件夹：存放博客文档
index.html：项目首页

更多高级操作：
[基于Hexo搭建个人博客——进阶篇（从入门到入土）](https://yangbingdong.com/2017/build-blog-hexo-advanced/)  
[Github+Jekyll添加评论支持](http://blog.csdn.net/ljinddlj/artical/details/52273652?utm_source=blogxgwz1)
[Liquid语法](https://www.jianshu.com/p/4224b8ea0ec0)  
[jekyll官方提供的一个博客编辑器](http://jekyllwriter.com/)  
[使用hexo，如果换了电脑怎么更新博客？](https://www.zhihu.com/question/21193762)

  


