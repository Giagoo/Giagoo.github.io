---
title: 自建ssr服务器
date: 2020-02-25 13:47:43
tags: 学习笔记
---
## Dependencies

* Reference:<https://github.com/Alvin9999/new-pac/wiki/%E8%87%AA%E5%BB%BAss%E6%9C%8D%E5%8A%A1%E5%99%A8%E6%95%99%E7%A8%8B>

* [Xshell](https://www.netsarang.com/zh/downloading/?token=VXZpSDlMaEtJZVZFaGJxTi1laEdhZ0BBV1JPaVVURTBTeVAxaUVwekZOMWN3)

* [ShadowsocksR](https://github.com/shadowsocksr-backup/shadowsocksr-csharp/releases)

<!--more-->

脚本1：

yum -y install wget

wget -N --no-check-certificate <https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh> && chmod +x ssr.sh && bash ssr.sh

脚本2：

yum -y install wget

wget --no-check-certificate <https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh>

chmod +x shadowsocksR.sh

./shadowsocksR.sh 2>&1 | tee shadowsocksR.log

一键加速VPS服务器
总共有2种加速方法，锐速加速和bbr加速，选择1种。
【加速教程1：破解版锐速加速教程】

此加速教程为破解版锐速加速,Vultr的服务器centos6系统官方进行了更新，导致目前不支持BBR的部署，但锐速应该是可以部署的，故增加了此部署脚本，加速后对速度的提升很明显，所以推荐部署加速脚本。该加速方法是开机自动启动，部署一次就可以了。

第一步，先更换服务器内核（脚本只支持centos系统，其它系统可以直接尝试第二步）

yum -y install wget

wget --no-check-certificate <https://blog.asuhu.com/sh/ruisu.sh> && bash ruisu.sh

完成后会重启，2分钟后重新连接服务器，连上后开始第二步的操作。

第二步，一键安装锐速

wget -N --no-check-certificate <https://raw.githubusercontent.com/91yun/serverspeeder/master/serverspeeder-all.sh> && bash serverspeeder-all.sh

卸载加速代码命令为：

chattr -i /serverspeeder/etc/apx* && /serverspeeder/bin/serverSpeeder.sh uninstall -f

出现running字样即可!
