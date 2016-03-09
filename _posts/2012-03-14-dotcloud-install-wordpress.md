---
layout: post
title:  "体验DotCloud部署wordpress"
date:   2012-03-14 09:48:09
categories: 云存储
Tags: 
 - dotcloud
 - wordpress
---  

我落伍了，现在才接触到cloud。

除了这个我个人的blog，去年开始还另外建了一个blog专门纪录一些与苹果mac iphone有关的东西，当时免费放在sinaapp上([http://chztv.sinaapp.com](http://chztv.sinaapp.com))。

随着新浪SAE政策的改变，不再免费赠送云豆，以后的日子难过了，于是寻找一些新的cloud，又能支持wordpress。

前几天看到了dotcloud，于是开始体验。

主要参考了这篇文章（http://blog.yangtse.me/2011/10/wordpress-dotcloud/），然后按步就班，基本上没问题。

我用x60的新苹果系统，很方便的安装了dotcloud，不用像在windows下要安装一大堆东西。

说几点dotcloud使用中的几点问题：

1.不像普通的虚拟主机，dotcloud需要在本地搭建dotcloud，然后通过命令行进行远程操作，当然命令很简单，输入dotcloud -h 都有帮助。

2.使用了nginx，和apache有较大不同，当然主要是指配置文件方面。建好wordpress后，第一次设置永久链接时，可能操作太快，少打了最前面的"/"，结果导致无法打开，502错误。后来只能删除数据库，重新安装wordpress。

3.dotcloud官方只能push，无法下载服务端文件

下面说说如何使用SSH客户端直接连接dotcloud服务器，进行文件管理。

1.获得ssh连接参数;

  输入 dotcloud info yourapp.www  就会显示如下图所示的信息

[![dotcloud-ssh](http://farm8.staticflickr.com/7183/6980821157_9a14e2e028.jpg)](http://www.flickr.com/photos/75898269@N04/6980821157/ "Flickr 上 Paul SAE Blog 的 dotcloud-ssh")

登录帐号：dotcloud

host:项目名-用户名.dotcloud.com

端口:每个项目都不一样，此项目是1488（具体看你的app信息)

private key：～/.dotcloud/dotcloud.key (私钥文件，找不到这个，暂时没有办法使用ssh管理。我用的是osx，直接在Finder中的转到文件夹功能，输入"～/.dotcloud/"，就打开了这个隐藏目录，很方便）

2.使用Tunnelier这个SSH客户端

  下载了TunnelierPortable便携版，解压即可使用。在 user keypair manager中导入私钥key文件，然后在登录认证选项中选择 publickey - slot1(这个具体按你的keypair manager中key位置决定)。OK，后面就简单了，登录后和普通的FTP一样操作了，想方便的可以直接上传下载文件了。

展示一下我的dotcloud项目：

[http://www.paulblog.tk](http://www.paulblog.tk "Mac iPhone app 技术研究")

[![Paul s Blog](http://farm8.staticflickr.com/7178/6980845211_d82a8c54d9.jpg)](http://www.flickr.com/photos/75898269@N04/6980845211/ "Flickr 上 Paul SAE Blog 的 Paul s Blog")