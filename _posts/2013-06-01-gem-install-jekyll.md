---
layout: post
title: "使用Gem安装Jekyll"
description: ""
category: 
tags: [gem, ruby, jekyll]
---
{% include JB/setup %}

### 安装

在Mac OS X 10.8.3操作系统下，默认已经安装了Ruby，Gem，因此，很简单，运行命令

	gem install jekyll

若遇到提示对系统没有写入权限，则可以

	sudo gem install jekyll
	
到此，若没有提示出现问题，则已经成功安装。

### 错误

但是，若没有问题，你还认为能见到这篇东东吗？本人前后尝试了安装3天，开始时候以为网络环境问题（GFW你懂的）在安装依赖包时都有不少Error发生，甚至早上7点时候也未能正确安装。碰到的问题主要是这个：

#### SSL错误

	ERROR: While executing gem ... (OpenSSL::SSL::SSLError)
	
经过一番Google，发现在[Github](https://github.com/rubygems/rubygems/issues/515)上也有关于此的一堆讨论，有通过升级Ruby和Gem版本解决的，有通过重装系统解决的（我擦~）。但其实分析发现，这里提示SSL错误，很可能是SSL配置上的问题，这里SSL配置有服务器或客户端方面的。并且，通过

	gem source
	
	*** CURRENT SOURCES ***
	https://rubygems.org/

可以看到，Gem通过https的链接进行包下载，那么，若把source设置成http的链接，就把问题解决了~

此时，通过以下命令安装

	gem install jekyll --source http://rubygems.org/

终于成功安装！

#### 提示Gem版本过低

若遇到这个提示，按照提示，升级Gem版本即可

	sudo gem update --system
	

### 一些

对于Ruby，我完全没有基础，从来只是只闻其声不见其本质。至此，能解决安装Jekyll的问题，也就为了能在本机看到生成后的页面，不用等Github的Pages生成时间。

PS. Jekyll 1.0.2后运行方式改为

	jekyll serve

之后通过访问[http://localhost:4000/](http://localhost:4000)访问