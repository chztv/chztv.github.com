---
title: 如何使用 Google Reader API 导出全部加星收藏和博客文章备份
author: Paul
layout: post
categories:
  - 技术前沿
tags:
  - google,Reader,导出
---

Google Reader 将于 7 月 1 号关闭的消息已经铺天盖地，微博，Twitter 上<a href="http://e.weibo.com/1750070171/znmt2yTJa" target="_blank">#寻找Google Reader替代品#</a> 还没有很好的结论，我们还在关注跟进。

<img style="display: block; margin-left: auto; margin-right: auto;" src="http://img7.chztv.com/blog/2013-0103/gr-out.jpg" alt="" width="669" height="300" />

从 Google Reader 导出数据不仅仅是订阅列表，更重要的是订阅的文章内容，比如 GR 上的加星收藏（Google 提供的<a href="https://www.google.com/takeout/#custom:reader" target="_blank">数据导出功能</a>，可以导出 GR 的笔记和加星文章，不过都是 json 格式数据，非技术人员无法直接查看）；还有很多人写过 BSP 或独立博客（虽然很长时间没更新，甚至忘记了），如果你或者其他人在 GR 上订阅过自己的博客，那么 GR 上会有你的文章内容备份，如何导出文章内容是更紧要的。使用 Google Reader API，你可以下载某个 Feed 订阅的全部内容。

1. 访问 <a href="https://www.google.com/reader/view/#overview-page" target="_blank">GR</a>（登录相关 Google 帐号）；
   
2. 获取相关信息：下载加星条目，先查找用户ID ：点击左侧导航，查看&ldquo;所有条目&rdquo;下的&ldquo;加星标的条目&rdquo;，进入后在浏览器 URL 中可以看到包含了你的用户ID(如加粗部分)： &#8230;/#stream/user%2F13125970274861303646%2Fstate&#8230; (也可以直接查看页面源代码，查找关键字 *USER*ID = )下载博客数据，先找到你的 Feed 地址（可以搜索相关博客名称）。可以从订阅列表中找到你的博客，从&ldquo;供稿设置&rdquo;中查看&ldquo;明细和统计信息&rdquo;：  
   
   ![][1]&nbsp;
   
3. 下载数据  
   
   下载加星条目，把第二步中的用户 ID 加入到下面的 URL 中替换&ldquo;你的用户ID&rdquo;：

> https://www.google.com/reader/atom/feed/http://www.google.com/reader/public/atom/user/你的用户ID/state/com.google/starred?n=1000

（加星条目超过 1000 条，需加入参数 c 翻页下载，为不拉长全文，请评论提出）  

- 下载博客，将你的 Feed 订阅地址替换&ldquo;你的 Feed 地址订阅地址&rdquo;：

> https://www.google.com/reader/atom/feed/你的 Feed 地址订阅地址?n=1000

（博客文章超过 1000 篇，可以用加入参数 &c=N 翻页）

下载的数据可以直接拖到支持查看 RSS 的浏览器中查看。如果您有更好的查看方式，也请在评论中告诉我。真希望 Google 不要关闭 Reader，也省了这么多麻烦。。

更新：

草木： 翻页的参数 c=xxx 是要用上面那个地址所得到的 XML 里 gr:continuation 里的那串字符。

[1]: http://img7.chztv.com/blog/2013-0103/gr-temp1.png