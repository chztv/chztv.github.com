---
title: 折腾Ghost博客
author: Paul
layout: post
dsq_thread_id:
  - 2936726860
categories:
  - 技术前沿
tags:
  - Ghost
  - Node.js
--- 

![Ghost博客](http://img7.chztv.com/2014-0709/tryghost.jpg)

和同事一起合租了一个 <[digitalocean.com](http://www.digitalocean.com)> 的VPS。以前自己的VPS打算最近就停止续费，主要的几个Blog相继迁往SAE等处。

一起有想法使用目前技术主流的静态博客，但折腾太麻烦，退而求其次，怎么着也得是Ghost之流的，WP实在是太老的，虽然通过插件支持MD，那还不如直接选新型主流Blog程序。

于是在DO上搭建好了Node.js环境，Ghost部署也几乎没遇到问题，然后就想不如打Wordpress的文章导入Ghost试试，结果失败。先是遇到了slug字段限制问题，这个倒是解决了，最终卡在了 

> SQLITE*CONSTRAINT: NOT NULL constraint failed: posts.created*at

MS发贴时间有Null，但有几百条的帖子，怎么看得过来啊～先放一放，有空再研究导入的问题～
