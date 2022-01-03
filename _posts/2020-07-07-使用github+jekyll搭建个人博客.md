---
layout: post
title: 使用github+jekyll搭建个人博客
description: github pages; jekyll; 
---

### 引言
本文将以一个拥有域名djames.com的用户James为例，简单介绍如何创建个人博客.<br><br><br>


### 具体步骤
#### 一.申请一个github账号
访问github.com，按照提示申请github账号，假设用户名为gjames.<br><br><br>


#### 二.在github上创建一个库
在github个人主页中找到Repositories，点击New Repositories创建一个新的库.库的名称前缀要与github账号相同，例如James需要创建名为gjames.github.io的库.<br><br><br>


#### 三.将个人域名连接到Github Pages网站(可跳过)
到个人域名管理界面添加CNAME格式的DNS解析记录，前缀为www，并将gjames.github.io添加到服务器名称.<br>
到新建的库的settings当中找到Github Pages设置，在Custom domain当中输入www.djames.com，并勾选Enforce HTTPS的选项.<br>
等待Github Pages设置页面出现`your site is published at https://www.djames.com/`的绿色提示信息，代表连接成功.（可能需要几分钟时间）<br><br><br>


#### 使用github desktop进行网站配置
先在github官网下载Github Desktop应用软件，安装后登录到gjames的账号，打开后在左上角选择File-clone repositories-gjames.github.io，等待代码下载完毕.<br>
接下来下载并安装配置文件到本地gjames.github.io的文件夹.
到ruby官网下载Ruby+Devkit，安装后在cmd当中执行:
{% highlight js %}
gem install jekyll bundler
{% endhighlight %}
接着在cmd当中进入gjames.github.io的项目路径（如果不知道路径可以在github desktop当中查看），执行以下命令:
{% highlight js %}
jekyll new . --force
{% endhighlight %}
完成后jekyll会在你的指定路径生成配置文件，你可以使用`bundle exec jekyll serve`命令预览你的网站.（使用指令后在浏览器访问127.0.0.1:4000）<br><br><br>


#### 为自己的博客选择并安装主题
默认的界面十分简陋，如果有功能或形象上的要求可以在主题网站中自选主题安装，这里列举三个网站:<br>
[网站1](https://jekyllthemes.io/)<br>
[网站2](http://jekyllthemes.org/)<br>
[网站3](http://themes.jekyllrc.org/)<br>
一般步骤为先将主题压缩包下载到本地，解压后复制到本地的gjames.github.io的项目路径内（覆盖原文件），再通过github desktop将更新后的项目上传到github网站上自己的库当中即可.<br>
有些主题需要按照作者提供的安装步骤进行安装，在此不做赘述.
<br><br><br>

#### 上传博客文章
选择一个Markdown文本编辑器，如Atom，VSCode，typora等.在编辑器中编辑本地gjames项目中_posts文件夹当中的文件，再通过github desktop上传到github上即可.
文章的文件名格式需严格遵循以下格式：
{% highlight js %}
2020-07-07-title.md
{% endhighlight %}
同时文章内容格式要求如下:
{% highlight js %}
---
layout: post
title: how to build a blog
---
content
{% endhighlight %}
<br><br><br>

### 知识点
* DNS解析记录有A格式与CNAME格式等.
* 对本地hosts文件进行编辑可以提高github运行速度.
* 代码管理（博客上传）有git和github desktop两种方式，本文采用较为简单的第二种.
* 几个简单的cmd命令:<br>进入其他分区`d:`<br>进入当前路径下文件夹`cd github\gjames.github.io`<br>返回上一级文件夹`cd .. `<br>返回当前分区根目录`cd\`
* 博客（网站）项目中通常包含以下几个文件:<br>主题的关键配置文件`_config.yml`<br>博客文章存储文件夹`_posts`<br>博客主页布局文件`index.html`
<br><br><br><br><br><br><br><br><br><br>

### 2021/1/3 更新
由于域名过期，原网站主题使用的库未进行更新，导致网站崩溃.今日对网站进行了调整，改用一个简单易用的网站主题.过程中，遇到了baseurl对url进行干扰的情况，将baseurl注释掉之后恢复正常.


### 参考文章
[如何在Github上写博客-知乎问题-少数派的回答](https://www.zhihu.com/question/20962496/answer/677815713)<br>
[Github Pages(一): 一个最基础的个人网站-简书-hans2936的文章](https://www.jianshu.com/p/f82c76b90336)<br>
[windows安装jekyll步骤及问题-CSDN博客-彭世瑜的文章](https://blog.csdn.net/mouday/article/details/79300135)
