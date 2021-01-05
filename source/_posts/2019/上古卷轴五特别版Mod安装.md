---
title: 上古卷轴五特别版Mod安装
date: 2019-06-21 23:55:39
tags: 游戏
---
## 索引

上古卷轴5特别版安装教程

<!--more-->

## [Mo Organizer 2](https://www.nexusmods.com/skyrimspecialedition/mods/6194)

## 自动安装

1. 不应安装在系统保护的文件夹中，例如Programs Files(×86)
2. 避免在游戏文件夹中安装MO2，因为这会导致VFS库出现问题  

## 手动安装更新

1. 转到MO2的安装目录，删除除了 \downloads, \mods, \profiles, \overwrite, ModOrganizer.ini and categories.dat以外的所有文件
2. 将新版本解压至此位置
3. 启动MO2
MO2依赖MSVC2017才能运行，如果没有你必须下载并安装：  
[VC redist x64](https://go.microsoft.com/fwlink/?LinkId=746572)  
[VC redist x86](https://aka.ms/vs/15/release/VC_redist.x86.exe)  
如果你不是WIN10系统，你可能还需要安装：  [https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows)

## [SKSE64](http://skse.silverlock.org/)

## 安装与卸载

安装：将压缩包中的所有文件解压至SSE根目录  
卸载：删除解压出的所有文件

## [LOOT](https://www.nexusmods.com/skyrimspecialedition/mods/1918)

## 安装和卸载

可以使用自动安装或手动安装，自动安装只需运行安装向导即可，手动安装请解压至你选择的位置，然后下载并安装[MSVC 2015 x86 redistributable](https://download.microsoft.com/download/6/A/A/6AA4EDFF-645B-48C5-81CC-ED5963AEAD48/vc_redist.x86.exe)  
如果使用安装程序安装了LOOT，则使用“开始”菜单中链接到的卸载程序卸载LOOT（可执行文件名为“unins000.exe”）。如果手动安装了LOOT:

1. 删除解压出的文件

2. 删除本地应用程序数据文件夹中的LOOT文件夹，可以通过在Windows文件资源管理器中输入％LOCALAPPDATA％来访问该文件夹。

## [CBP Physics](https://www.nexusmods.com/skyrimspecialedition/mods/13207)

## 兼容与不兼容

0.20兼容1.5.39和SKSE 2.0.7  
VR版本兼容SyrimVR 1.4.15和SKSE 2.0.10  
0.04之前的版本在ENB和Reshade方面存在问题  
0.18之前的版本HDT高跟鞋存在问题，CBP是第二个加载的

## 需求

1. Skyrim SE 1.5.39
2. SKSE64 2.0.7
3. XP32 Maximum Skeleton Special Extended - XPMSSE
4. FNIS
5. 你必须使用HDT SKELETON,不是BBP版，可用于4.2
6. 需要具有用于乳房/臀部/腹部的骨量的身体替代品，CBBE Physics只有胸部和臀部重量，所以它不会有任何腹部反弹。

## 安装

只需将DLL和CBPConfig.txt文件复制到Data / SKSE / Plugins

## 配置反弹

默认设置效果非常像果冻，很大程度上是因为它让我更容易看到什么不起作用，但整体外观可以显着改变。  
编辑数据/ SKSE /插件/ CBPConfig.txt  
将Tuning.rate设置更改为0以外的值  
Tuning.rate 60  
这决定了从文件重新读取配置的频率，60大约是1秒。  
启动游戏，编辑文件中的参数并保存，您应该在一两秒内看到更改。  
一旦你满意，将Tuning.rate更改为0，它将停止重新加载配置。  
如果您打算调整物理，则必须在运行“天际”之前将调整速率设置为0以外的值。  
从0.02开始默认禁用调优

## [BodySlide and Outfit Studio](https://www.nexusmods.com/skyrimspecialedition/mods/201)

1. MO2常规安装
2. 转到MO右侧的“数据”选项卡，导航到“CalienteTools / body slide / body slide x64 . exe”
3. 右键单击“BodySlide x64.exe”- >添加为可执行文件(确保是64位文件！)
4. 在可执行文件列表中选择“BodySlide”，并始终从这里运行它。

## [Fores New Idles in Skyrim SE - FNIS SE](https://www.nexusmods.com/skyrimspecialedition/mods/3038)

1. MO2常规安装
2. 转到MO右侧的“数据”选项卡，导航到tools/GenerateFNIS_for_Users/GenerateFNISforUsers.exe
3. 右键单击“GenerateFNISforUsers.exe”- >添加为可执行文件
4. 在可执行文件列表中选择“GenerateFNISforUsers.exe”，并始终从这里运行它。
