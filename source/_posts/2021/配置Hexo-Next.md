---
title: 配置Hexo Next
copyright: true
comments: true
date: 2021-01-08 18:34:03
tags: Hexo
categories: 博客
---
## 切换主题

在Hexo根目录下找到_config.yml，切换主题为Next

```bash
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: Next
```

<!--more-->

## 站点设置

```bash
title: BUSHLAND # 网站标题
subtitle: We are never met but, Can we have a coffee or something? #网站副标题
description: My Place # 网站描述
keywords: # 关键词
author: JiahaoChen # 网站作者
language: zh-CN # 语言
timezone:  # 时区
```

## 新建标签页

1. 新建Tags标签页：hexo new page "tags"(其他标签页同理)  

2. 公益404：在新建的404.html下填入以下代码:  

```bash
title: 404 Not Found：该页无法显示
toc: false
comments: false
permalink: /404
---
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>404</title>
    </head>
    <body>
        <script type="text/javascript" src="//qzonestyle.gtimg.cn/qzone/hybrid/app/404/search_children.js" charset="utf-8" homePageUrl="/" homePageName="返回"></script> 
    </body>
</html>
```

## 添加站内搜索功能

安装插件：`npm install hexo-generator-searchdb --save`  

修改主题配置文件_config.yml:

```bash
# Local Search
# Dependencies: https://github.com/theme-next/hexo-generator-searchdb
local_search:
  enable: true
  # If auto, trigger search by changing input.
  # If manual, trigger search by pressing enter key or search button.
  trigger: auto
  # Show top n results per article, show all results by setting to -1
  top_n_per_article: 1
  # Unescape html strings to the readable one.
  unescape: true
  # Preload the search data when the page loads.
  preload: true
```

## 设置网站头像

```bash
# Sidebar Avatar
avatar:
  # 头像文件存放地址theme/next/source/images/avatar.gif
  url: /images/avatar.gif
  # 圆形显示头像
  rounded: true
  # 旋转头像
  rotated: true
```

## 设置侧栏链接

```bash
# Social Links
# Usage: `Key: permalink || icon`
# Key is the link label showing to end users.
# Value before `||` delimiter is the target permalink, value after `||` delimiter is the name of Font Awesome icon.
social:
  GitHub: https://github.com/Giagoo || fab fa-github
  E-Mail: mailto:jiahaosmail@163.com || fa fa-envelope
  #Weibo: https://weibo.com/yourname || fab fa-weibo
  #Google: https://plus.google.com/yourname || fab fa-google
  #Twitter: https://twitter.com/yourname || fab fa-twitter
  #FB Page: https://www.facebook.com/yourname || fab fa-facebook
  #StackOverflow: https://stackoverflow.com/yourname || fab fa-stack-overflow
  YouTube: https://www.youtube.com/channel/UCpyKQ9Q4Nab1iVn_3t0uNNA || fab fa-youtube
  #Instagram: https://instagram.com/yourname || fab fa-instagram
  #Skype: skype:yourname?call|chat || fab fa-skype
  Artstation: https://www.artstation.com/jiahaochen || fab fa-artstation
  Pinterest: https://www.pinterest.com/jiahaochenpin/_saved/ || fab fa-pinterest
  Bilibili:  https://space.bilibili.com/37746460 || fab fa-youtube
```

## 帖子设置版权说明

```bash
# Creative Commons 4.0 International License.
# See: https://creativecommons.org/share-your-work/licensing-types-examples
# Available values of license: by | by-nc | by-nc-nd | by-nc-sa | by-nd | by-sa | zero
# You can set a language value if you prefer a translated version of CC license, e.g. deed.zh
# CC licenses are available in 39 languages, you can find the specific and correct abbreviation you need on https://creativecommons.org
creative_commons:
  license: by-nc-sa
  sidebar: true
  post: true
  language: deed.zh
```

在帖子中新增：copyright: true  

## 设置友情链接

```bash
# Blog rolls
links_settings:
  icon: fa fa-link
  title: Links
  # Available values: block | inline
  layout: block

links:
  Title: http://yoursite.com
```

## 侧栏添加网易云音乐

在网易云音乐中分享你的歌单，在你的动态中找到歌单生成外部链接，复制外部链接代码，插入至`themes\next\layout\_macro\sidebar.swig`文件末尾

## 添加Addthis分享

```bash
# AddThis Share. See: https://www.addthis.com
# 前往 https://www.addthis.com/dashboard 自定义分享工具，获取ID
add_this_id: your id key
```

## 添加Tidio留言

```bash
chat:
  enable: true
  #service: chatra
  service: tidio
  icon: fa fa-comment # Icon name in Font Awesome, set false to disable icon.
  text: Wait,I know you # Button text, change it as you wish.
```

```bash
# Tidio Support
# See: https://www.tidiochat.com
# Dashboard: https://www.tidiochat.com/panel/dashboard
# Public Key, get it from dashboard. See: https://www.tidiochat.com/panel/settings/developer
tidio:
  enable: true
  key: Public Key
```

## 不算子统计

```bash
# Show Views / Visitors of the website / page with busuanzi.
# Get more information on http://ibruce.info/2015/04/04/busuanzi
busuanzi_count:
  enable: true
  total_visitors: true
  total_visitors_icon: fa fa-user
  total_views: true
  total_views_icon: fa fa-eye
  post_views: true
  post_views_icon: fa fa-eye
```

## 帖子字数统计

安装插件：`npm install hexo-symbols-count-time --save`

主题配置文件_config.yml（next.yml） 修改如下:

```bash
symbols_count_time:
  separated_meta: true  # false会显示一行
  item_text_post: true  # 显示属性名称,设为false后只显示图标和统计数字,不显示属性的文字
  item_text_total: true # 底部footer是否显示字数统计属性文字
```

## 底部红心跳动，作者

```bash
footer:
  # Specify the date when the site was setup. If not defined, current year will be used.
  since: 2018 # 网站开始运行时间

  # Icon between year and copyright info.
  icon:
    # Icon name in Font Awesome. See: https://fontawesome.com/icons
    name: fa fa-heart # 爱心图标
    # If you want to animate the icon, set it to true.
    animated: true # 爱心跳动动画
    # Change the color of icon, using Hex Code.
    color: "#ff0000" #爱心颜色

  # If not defined, `author` from Hexo `_config.yml` will be used.
  copyright:  # 作者

  # Powered by Hexo & NexT
  powered: false # 由Hexo强力驱动开启与关闭
```

## 代码复制与显示风格

```bash
codeblock:
  # Code Highlight theme
  # Available values: normal | night | night eighties | night blue | night bright | solarized | solarized dark | galactic
  # See: https://github.com/chriskempson/tomorrow-theme
  highlight_theme: normal
  # Add copy button on codeblock
  copy_button:
    enable: true
    # Show text copy result.
    show_result: true # 复制成功提示
    # Available values: default | flat | mac
    style: mac # 代码显示风格
```

## Valine评论

在LeaCloud注册并登录（左上角国际版），进入控制台创建应用，获取Appid和Appkey

```bash
# Valine
# For more information: https://valine.js.org, https://github.com/xCss/Valine
valine:
  enable: true
  appid: your appid
  appkey: you app key
  notify: false # Mail notifier
  verify: false # Verification code
  placeholder: Just go go # Comment box placeholder
  avatar: mm # Gravatar style
  guest_info: nick,mail,link # Custom comment header
  pageSize: 10 # Pagination size
  language: # Language, available values: en, zh-cn
  visitor: false # Article reading statistic
  comment_count: true # If false, comment count will only be displayed in post page, not in home page
  recordIP: false # Whether to record the commenter IP
  serverURLs: # When the custom domain name is enabled, fill it in here (it will be detected automatically by default, no need to fill in)
  #post_meta_order: 0
```

在tags等标签页中关闭评论：comments: false

## 开启其他发布渠道

```bash
# Subscribe through Telegram Channel, Twitter, etc.
# Usage: `Key: permalink || icon` (Font Awesome)
follow_me:
  Bilibili: https://space.bilibili.com/37746460 || fab fa-youtube
  Artstation: https://www.artstation.com/jiahaochen || fab fa-telegram
  #WeChat: /images/wechat_channel.jpg || fab fa-weixin
  RSS: /atom.xml || fa fa-rss
```

## 开启打赏

```bash
# Reward (Donate)
# Front-matter variable (unsupport animation).
reward_settings:
  # If true, reward will be displayed in every article by default.
  enable: true
  animation: false
  comment: Donate comment here.

reward:
  wechatpay: /images/wechatpay.png
  #alipay: /images/alipay.png
  #paypal: /images/paypal.png
  #bitcoin: /images/bitcoin.png
```

## 阅读全文

1. 手动添加：在要截断的位置添加<!--more-->_(推荐)_

2. 安装插件：`npm install hexo-excerpt --save`  
在站点配置文件_config.yml中添加：

```bash
# 自动添加阅读全文
excerpt:
depth: 1
excerpt_excludes: []
more_excludes: []
hideWholePostExcerpts: true
```

## 背景彩带

在<https://github.com/theme-next/theme-next-canvas-ribbon>下载源码

```bash
# Canvas-ribbon
# Dependencies: https://github.com/theme-next/theme-next-canvas-ribbon
# For more information: https://github.com/zproo/canvas-ribbon
canvas_ribbon:
  enable: true
  size: 300 # The width of the ribbon
  alpha: 0.6 # The transparency of the ribbon
  zIndex: -1 # The display level of the ribbon
```

## 3D动态背景

在<https://github.com/theme-next/theme-next-three>下载源码

```bash
# JavaScript 3D library.
# Dependencies: https://github.com/theme-next/theme-next-three
three:
  enable: false # 开启与关闭
  three_waves: false # 波浪形
  canvas_lines: false # 线形
  canvas_sphere: true # 球形
```
