---
layout: article
title: 使用Jekyll创建GitHub Pages站点
mathjax: true
tags: ["GitHub", "TeXt"]
---
简短快速地记录创建 GitHub Pages站点的过程，作为第一篇的内容。

笔记本操作系统是Windows 11。

注册和登录Github账号，安装Git、GitHub Desktop。此处略过。

参考[TeXt Theme文档](https://tianqi.name/jekyll-TeXt-theme/)，选择普通方式安装TeXt。

在安装开发环境这一步，本想使用Docker，但是卡在生成 *Gemfile.lock* 文件那一步，迟迟无法解决，最终还是选择了手动安装Ruby。

参考[在Winodws上運作jekyll](https://wcc723.github.io/jekyll/2014/01/13/windows-jekyll-server/)，进行到jekyll server这一步，报了“cannot load such file -- webrick (LoadError)”，参考[这个答案](https://github.com/jekyll/jekyll/issues/8523)，“Adding `gem "webrick"` to my Gemfile solves the problem”。

后来又报了“Permission denied - bind(2) for 127.0.0.1:4000 (Errno::EACCES) ”，原来是端口被占用，参考[这里](https://segmentfault.com/q/1010000010483290)将占用4000端口的进程关闭。

此时，可以访问http://localhost:4000/预览我对站点内容所进行的改动了，但是访问https://cestlete.github.io/，看到的并不是本地预览的首页内容，而是——

![wrong page2022-01-03 140311](../../../../../assets/images/wrong%20page2022-01-03%20140311.jpg){:.border.rounded}

原来是建站的分支不正确，从gh-pages改成master，即可以通过访问https://cestlete.github.io/看到我的GitHub Pages站点。

![branch master2022-01-03 140450](../../../../../assets/images/branch%20master2022-01-03%20140450.jpg){:.border.rounded}

![my github page 2022-01-03 144623](../../../../../assets/images/my%20github%20page%202022-01-03%20144623.jpg){:.border.rounded}

至此，建站的工作就完成了，这一篇算是试用发布文章的功能，至于其他的设置，以后再慢慢展开。毕竟最重要的是内容。

目前在文章里插入图片不是非常方便，也许是我还没有掌握技巧，还要继续学习。

两个小坑：

1.在命令窗口执行命令安装了什么之后，如果要查看版本验证是否安装成功，建议新开一个窗口，不然可能会即使安装成功也看不到版本号。

2.安装GitHub Desktop之后，拉取通过fork方式创建站点的库，进入本地USERNAME.github.io文件夹之后右键打开Windows终端再启动Jekyll。


参考链接：

1.[用 Jekyll 在 GitHub 上搭建你的个人网站](https://sinantang.github.io/a%20developer%20guide%20for%20newbies%20-%20starting%20with%20python/2017/09/23/building-your-own-static-site-using-jekyll/)

2.[用 Github pages 和 Jekyll 搭建博客](https://yuleii.github.io/2020/06/09/build-blog-with-github-pages-and-jekyll.html)

3.[Creating a GitHub Pages site with Jekyll](https://docs.github.com/cn/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)

4.[在Winodws上運作jekyll](https://wcc723.github.io/jekyll/2014/01/13/windows-jekyll-server/)

5.[Jekyll serve fails on Ruby 3.0](https://github.com/jekyll/jekyll/issues/8523)

6.[Rails: Permission denied - bind(2) for "127.0.0.1" port 3000 (Errno::EACCES)](https://stackoverflow.com/questions/43739386/rails-permission-denied-bind2-for-127-0-0-1-port-3000-errnoeacces)

7.[Jekyll 搭建 Blog 上传到 Github，访问总是报错 404？](https://www.zhihu.com/question/39820273)
