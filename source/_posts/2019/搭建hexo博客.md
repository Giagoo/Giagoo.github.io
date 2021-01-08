---
title: 搭建hexo博客
date: 2019-06-21 22:35:00
tags: 学习笔记
---
## 创建github个人仓库

注册GitHub帐号，点击GitHub中的New repository创建新仓库，仓库名应该为：`username.github.io`(固定写法)

<!--more-->

## 安装Git

[Downlaod Git](https://git-scm.com/download/)

配置Git邮箱和用户名

```git
git config --global user.name "你的GitHub用户名"  
git config --global user.email "你的GitHub注册邮箱"
```

生成密钥文件，已有需删除或修改

```git
ssh-keygen -t rsa -C "你的GitHub注册邮箱"
```

连续三个回车，在用户名文件夹下新生成的.ssh文件夹下找到生成的.ssh的文件夹中的id_rsa.pub密钥，将内容全部复制

登录你的Github，打开GitHub_Settings_keys 页面，新建new SSH Key，将刚刚复制的id_rsa.pub内容粘贴进去，最后点击Add SSH key。

检测链接是否成功

```git
ssh git@github.com
```

## 安装Node.js

[Download Node.js](https://nodejs.org/en/download/)

Hexo基于Node.js,安装Node.js会包含环境变量及npm的安装，安装后

检测Node.js是否安装成功，在命令行中输入

```cmd
 node -v
```

检测Npm是否安装成功，在命令行中输入

```cmd
npm -v
```

## 安装Hexo

在电脑中创建你的博客文件夹，Hexo框架与你自己发布的网页都在这个文件夹中。创建好后，进入文件夹中，按住shift键，右击鼠标点击“在此处打开一个Powershell窗口”

使用npm命令安装Hexo：

```npm
npm install -g hexo-cli
```

安装完成后，初始化博客:

```hexo
hexo init blog
```

新建博文：

```hexo
hexo new "new bolg"
```

生成：

```hexo
hexo g
```

推送：

```hexo
hexo d
```

## 将博客上传至Github

打开站点的配置文件_config.yml，翻到最后修改并保存为：

deploy:  
type: git  
repo: 这里填入你之前在GitHub上创建仓库的完整路径，记得加上 .git  

安装Git部署插件：

```npm
npm install hexo-deployer-git --save
```

清理，生成，推送:

```hexo
hexo clean  
hexo g  
hexo d
```

## 更换主题

[Hexo官方主题网站](https://hexo.io/themes/)

打开站点配置文件，找到：

> #Extensions  
> Plugins: hexo-generate-feed  
> ##Themes: <https://hexo.io/themes/>  
> theme: hexo-theme-icalm

将theme后的主题更换为你想要的已经下好的主题的名字

## 备份与恢复

### 备份

1. 创建新仓库，如果同名仓库之前已经创建，请将之前的仓库改名，新建的仓库必须是Username.github.io；  

2. 创建两个分支：master和hexo；  

3. 设置hexo为默认分支；  

4. 将刚刚创建的新仓库clone至本地，将之前的hexo文件夹中的_config.yml，themes/，source/，scaffolds/，package.json，.gitignore复制至WincerChan.github.io文件夹；  

5. 将themes/next/(我用的是NexT主题)中的.git/删除，否则无法将主题文件夹push；  

6. 在Yourname.github.io文件夹执行`npm install`和`npm install hexo-deployer-git`（这里可以看一看分支是不是显示为hexo）；  

7. 执行`git add` ,`git commit -m`,`git push origin hexo`来提交hexo网站源文件；执行hexo g -d生成静态网页部署至Github上。  

### 恢复

1. 使用git clone git@github.com:WincerChan/WincerChan.github.io.git将仓库拷贝至本地；  

2. 切换分支：git checkout hexo  

3. 在文件夹内执行以下命令`npm install hexo-cli -g`、`npm install`、`npm install hexo-deployer-git`。

## 对文章进行年份分类

在_config.yml中将new_post_name:修改为： :year/:title

## fatal: refusing to merge unrelated histories解决

原因是两个分支是两个不同的版本，具有不同的提交历史  

git pull origin master --allow-unrelated-histories  (会将两个分支合并，慎用)  

可以允许不相关历史提，强制合并
