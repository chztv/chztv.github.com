---
layout: post
title:  "分析百度网盘真实下载地址"
categories: 
 - 云存储
tags: 
 - aria2 
 - 旋风 
 - 百度 
 - 网盘 
 - 迅雷
--- 
 
百度网盘最近发力，各大论坛用百度网盘来分享高清的也越来越多，可惜百度网盘不支持第三方下载工具，而我又最喜欢用Aria2来下载，怎么办呢？这个难不倒我，分析一下，应该是很easy的。

先拿一个例子来分析，[http://pan.baidu.com/share/link?shareid=3014&uk=1479460145](http://pan.baidu.com/share/link?shareid=3014&uk=1479460145)，这是一个TVB近期剧集《造王者》的分享地址。用Chrome来打开，选中要下载的链接，只有js弹出的下载按钮，看不到真实地址。没关系，打开Chrome自带的审核元素界面，选中“Network”的Tab，然后点击百度网盘的下载链接，浏览器会弹出保存界面，没事，关了他（我们不用浏览器来下载）。这时，审核元素的表里，应该有一个红色的元素，就是我们要下载的文件的，在上面单击右链，复制URL。OK，这个就是百度网盘的真实链接了。当然，光用这个url只能在当前浏览器中下载，其他下载工具是没法下的，因为没有对应的cookies。

我们接下来找这个cookies，继续在这个Network的窗口中，点一个其他的文件，比如排在最前面的dtcount，OK，右边出来一堆东西，选cookies，应该有一个BDUT打头的，我们要找的就是他了，把这个cookies的值复制，然后放到aria2的下载文件里，可以像我一样书写：

> http://www.baidupcs.com/file/%E6%88%91%E7%9A%84%E6%96%87%E6%A1%A3/HDJ.King.Maker.E03.720p.HDTV.x264-NGB.part1.rar?fid=1479460145-250528-333600737&time=1348298209&sign=FPDTAE-DCb740ccc5511e5e8fedcff06b081203-BUs048SZThTwxfYnyiLFfLjKok0%3D&expires=8h&digest=3a9db694bb38ca9a51beefe012f1270d
>

>   out=HDJ.King.Maker.E03.720p.HDTV.x264-NGB.part1.rar
>

>   header=Cookie: BDUT=3uqkD584757CF24AF69A1E5AA9C8E3138a70d414a1451
>

>   continue=true
>

>   max-connection-per-server=5
>

>   split=10
>

>   parameterized-uri=true

然后运行aria2用这个配置就可以下载百度网盘的文件了，是不是很easy……