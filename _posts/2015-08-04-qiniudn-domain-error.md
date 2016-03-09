---
title: 七牛qiniudn域名失效
author: Paul
layout: post
categories:
  - 技术
tags:
  - 七牛,域名
---  


自己这个Blog用的图片都是存在又拍云，然后又用了七牛的镜像功能，直接用自定义域名指向七牛。

下午在V2EX看到七牛的域名居然失效了，登录官网一看，果然！！！！

> 您好，*.qiniudn.com突然不能解析，我们正在全力跟域名托管商godaddy联系恢复中，为了业务不受影响，请尽快调整到自定义域名 或 qiniucdn 等其他域名。 
> 域名切换方案： 
> 1 使用 *.qiniudn.com 域名的，请切换至 *.clouddn.com 或 *.qiniucdn.com（登录portal.qiniu.com查看） 
> 2 CNAME到 *.qiniudn.com的用户，请更换CNAME的目标为qncdn.qiniudns.com，或其他控制台中标明的CNAME目标 
> 最新状态的跟踪请查看status.qiniu.com

现在只能更换原域名CNAME了，应该生效了，图片出来了