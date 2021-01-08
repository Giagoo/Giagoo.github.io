---
title: 自建ssr服务器
date: 2020-02-25 13:47:43
tags: 学习笔记
---
## Dependencies（旧版）

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

## 2018/1/8更新

### 安装脚本

```bash
yum -y install wget

wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh
```

查看安装命令：`bash.ssr.sh`

注意：如果创建的是centos7的服务器，需要使用命令关闭防火墙，否则无法使用代理。CentOS 7.0默认使用的是firewall作为防火墙。

查看防火墙状态命令：`firewall-cmd --state`

停止firewall命令：`systemctl stop firewalld.service`

禁止firewall开机启动命令：`systemctl disable firewalld.service`

### 一键加速VPS服务器

```bash
wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh"

chmod +x tcp.sh

./tcp.sh
```

脚本管理命令为：`./tcp.sh`

操作方法：

1. 先安装内核，重启vps让内核生效，再启动对应的加速即可。数字1的BBR/BBR魔改内核对应数字4、5、6的BBR加速、BBR魔改加速和暴力BBR魔改版加速。数字2的BBRplus内核对应数字7的BBRplus加速。数字3的锐速加速内核对应数字8的锐速加速。

2. 以安装暴力BBR魔改版加速为例，我们先安装对应的内核，输入数字1

3. 内核安装完成后，输入y进行重启，重启才能让内核生效

4. 重启完成后，输入数字6来启动暴力BBR魔改版加速

5. 输入./tcp.sh查看最终是否启动成功。

6. 如果想换一个加速，输入数字9进行卸载加速，然后进行同样的操作，安装内核再安装对应内核的加速即可。

7. 最后将浏览器的代理设置为（http）127.0.0.1和1080即可。账号的端口号就是你自己设置的，而要上网的浏览器的端口号是1080，固定的，谷歌浏览器可以通过 SwitchyOmega 插件来设置。
