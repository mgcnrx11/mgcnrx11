---
layout: post
title: "关于SSH的一些"
description: ""
category: 
tags: [ssh]
---
{% include JB/setup %}

## SSH介绍

## SSH配置
https://help.github.com/categories/56/articles
### Mac OS和Linux

### Windows
需要打开Git Bash或在msysGit的环境下
前段时间安装window下git时，在cygwin下遇到了“Could not open a connection to your authentication agent.”。

【解决方法】需要ssh-agent启动bash，或者说把bash挂到ssh-agent下面。

【具体方法】

islue@localhost $ ssh-agent bash --login -i
islue@localhost $ ssh-add
 

 【ssh-agent介绍】

ssh-agent就是一个管理私钥的代理，受管理的私钥通过ssh-add来添加，所以ssh-agent的客户端都可以共享使用这些私钥。

好处1：不用重复输入密码。

用 ssh-add 添加私钥时，如果私钥有密码的话，照例会被要求输入一次密码，在这之后ssh-agent可直接使用该私钥，无需再次密码认证。

好处2：不用到处部署私钥

假设私钥分别可以登录同一内网的主机 A 和主机 B，出于一些原因，不能直接登录 B。可以通过在 A 上部署私钥或者设置 PortForwarding 登录 B，也可以转发认证代理连接在 A 上面使用ssh-agent私钥登录 B。

islue@localhost $ ssh -A HOST_A
islue@HOST_A $ ssh HOST_B
islue@HOST_B $

### 常见错误
Error: Permission denied (publickey)
## SSH应用

### Github

#### Windows下用TortoiseGit

### 远程连接Linux主机

### SSH代理

### 文件传输