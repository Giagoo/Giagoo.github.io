---
title: 配置Hexo Next
copyright: true
comments: true
tags: Hexo
categories: Hexo
abbrlink: cdf1e5ae
date: 2021-01-08 18:34:03
image: https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2969235134,2098148338&fm=11&gp=0.jpg
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

## 圆角设置

在hexo/source/下新建_data文件夹，在此文件夹下新建variables.styl文件，写入代码：

```bash
// 圆角设置
$border-radius-inner     = 20px 20px 20px 20px;
$border-radius           = 20px;
```

此时在左下角会有小方块bug，在_data文件夹下新建styles.styl文件，写入代码：

```bash
.sidebar {
box-shadow: none
background: none
}
```

在主题配置文件下启用Custom文件

```bash
# Define custom file paths.
# Create your custom files in site directory `source/_data` and uncomment needed files below.
custom_file_path:
  #head: source/_data/head.swig
  #header: source/_data/header.swig
  #sidebar: source/_data/sidebar.swig
  #postMeta: source/_data/post-meta.swig
  #postBodyEnd: source/_data/post-body-end.swig
  #footer: source/_data/footer.swig
  #bodyEnd: source/_data/body-end.swig
  variable: source/_data/variables.styl
  #mixin: source/_data/mixins.styl
  style: source/_data/styles.styl
```

## 自定义颜色

在themes\next-7.7.2\source\css\_variables\base.styl文件中修改：

```bash
// Colors
// colors for use across theme.
// --------------------------------------------------
$whitesmoke   = #F79F81; // 菜单栏当前菜单，归档线条
$gainsboro    = #e3c6f0; // 菜单栏头像边框，分割线。单行代码块
$grey-lighter = #cccedd; // 菜单栏子标题
$grey-light   = #ab2acc; // 菜单栏文章计数器
$grey         = #6a2dbb; // 时间节点
$grey-dark    = #000000; // 菜单栏博主卡片区文字【描述|日志|分类|标签】
$grey-dim     = #9059bf;
$black-light  = #000000;  // 文章正文颜色
$black-dim    = #5b2293;
$black-deep   = #01A9DB;  // 菜单栏背景
$red          = #ff2a2a;
$blue-bright  = #87daff;
$blue         = #0684bd;
$blue-deep    = #262a30;
$orange       = #fc6423;
```

### 修改文章阅读进度条

修改主题配置文件：

```bash
# Reading progress bar
reading_progress:
  enable: true
  # Available values: top | bottom
  position: top
  color: "#01A9DB"
  height: 5px
```

## 永久性链接

安装：`npm install hexo-abbrlink --save`

在站点配置文件中修改：

```bash
-permalink: :year/:month/:day/:title/
+permalink: posts/:abbrlink/
+abbrlink:
+  alg: crc32  #support crc16(default) and crc32
+  rep: hex    #support dec(default) and hex
```

修改完成后，原链接从:year/:month/:day/:title/变为<https://giagoo.github.io/posts/cdf1e5ae/>

## 文章摘要图片

在主题配置文件中false Excerpt

```bash
# Automatically excerpt description in homepage as preamble text.
excerpt_description: false

# Read more button
# If true, the read more button will be displayed in excerpt section.
read_more_btn: false
```

在themes\Next\layout\_macro\post.swig中插入代码：

```bash
          <!--noindex-->
          {%- if theme.read_more_btn %}
            <div class="post-button">
              <a class="btn" href="{{ url_for(post.path) }}">
                {{ __('post.read_more') }} &raquo;
              </a>
            </div>
          {%- endif %}
          <!--/noindex-->
        {% elif post.excerpt %}
          {{ post.excerpt }}
  
 +        {% if post.image %}
 +        <div class="out-img-topic">
 +        <img src={{ post.image }} class="img-topic" />
 +        </div>
 +        {% endif %}

```

在hexo/source/_data/styles.styl中加入：

```bash
// 图片宽度统一
img.img-topic {
    width: 100%;
}
```

最后在帖子的front-matter（tags所在的区域）中加入一行：

image: url

## 自定义回到顶部

将图片素材放到source/images 目录下  
图片下载：<http://yearito.cn/images/scroll.png>

在自定义样式文件中添加一下代码：

```bash
//自定义回到顶部样式
.back-to-top {
  right: 60px;
  width: 70px;  //图片素材宽度
  height: 900px;  //图片素材高度
  top: -900px;
  bottom: unset;
  transition: all .5s ease-in-out;
  background: url("/images/scroll.png");

  //隐藏箭头图标
  > i {
    display: none;
  }

  &.back-to-top-on {
    bottom: unset;
    top: 100vh < (900px + 200px) ? calc( 100vh - 900px - 200px ) : 0px;
  }
}
```

## 添加豆瓣读书与电影

### 安装

`npm install hexo-douban --save`

### 配置

在站点配置文件下新增：

```bash
douban:
  user: your douban id
  builtin: true
  book:
    title: '读过的书籍'
    quote: '积书须善学,隙土可深耕'
  movie:
    title: '看过的电影'
    quote: '就像眼泪在雨中消逝一般'
  game:
    title: '玩过的游戏'
    quote: '恶就是恶，无论是大恶还是小恶。如果要让我在两者中选一个的话，我宁愿不选'
  timeout: 10000
```

### 使用

```bash
$ hexo douban -h
Usage: hexo douban

Description:
Generate pages from douban

Options:
  -b, --books   Generate douban books only
  -g, --games   Generate douban games only
  -m, --movies  Generate douban movies only
```

注意：安装了hexo douban之后，就不能用hexo d了，因为hexo douban跟hexo deploy的前缀都是hexo d，需要使用全称
