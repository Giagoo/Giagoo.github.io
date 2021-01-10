---
title: Compile Aseprite
tags: 学习笔记
abbrlink: 4f85d45a
date: 2020-05-05 20:06:50
---
## Windows dependencies

* Reference:<https://github.com/aseprite/aseprite/blob/master/INSTALL.md>

* Windows 10 (we don't support cross-compiling and don't know if this would be possible)  
* [Visual Studio Community 2019](https://visualstudio.microsoft.com/zh-hans/downloads/?rr=https%3A%2F%2Fgithub.com%2Faseprite%2Faseprite%2Fblob%2Fmaster%2FINSTALL.md)  
* The [Desktop development with C++ item + Windows 10.0.18362.0 SDK](https://imgur.com/a/7zs51IT) from the Visual Studio installer  

<!--more-->

## Dependencies  

* The latest version of [CMake](https://cmake.org/)  

> just click next next and next  

* [Ninja](https://ninja-build.org/) build system  

> unpack and put it in .../CMake/bin

* And a compiled version of the `aseprite-m81` branch of the [Skia library](https://github.com/aseprite/skia#readme). There are [pre-built packages available](https://github.com/aseprite/skia/releases). You can get some extra information in the laf dependencies page.  

> download `pre-built packages available` and put it in C/:deps  
> if you choice compiling skia by youself , you need download [Clang](http://releases.llvm.org/9.0.0/LLVM-9.0.0-win64.exe) and [Google depot tools](https://storage.googleapis.com/chrome-infra/depot_tools.zip), they should be install in C:/deps .  
please check it in :
<https://github.com/aseprite/skia#skia-on-windows>

* *In this case, C:\deps\skia is the directory where Skia was compiled or uncompressed.*

## Compiling

1. [Get Aseprite code](https://github.com/aseprite/aseprite/releases), put it in a folder like `C:\aseprite`, and create a `build` directory inside to leave all the files that are result of the compilation process (.exe, .lib, .obj, .a, .o, etc).

2. Open a developer command prompt or in the command line (cmd.exe) call:

    call "C:\Program Files (x86)\MicrosoftVisualStudio\2019\Community\Common7\Tools\VsDevCmd.bat"-arch=x64

3. and then

    cd aseprite  
    mkdir build  
    cd build  
    cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo -DLAF_BACKEND=skia-DSKIA_DIR=C:\deps\skia-DSKIA_LIBRARY_DIR=C:\deps\skia\out\Release-x64 -G Ninja..  
    ninja aseprite

4. wait it finish

百度网盘：

链接：<https://pan.baidu.com/s/1AHQhZBW-x_DB_FjJrL9DDQ>

提取码：9527
