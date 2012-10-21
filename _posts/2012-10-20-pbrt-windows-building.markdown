---
title: Building pbrt with VS2012
layout: post
guid: urn:uuid:silentlistener-2012-10-20-1958
tags:
  - pbrt
  - C++
  - Graphic
  - VS2012
---

<span class="label label-success">Preparation</span>  
首先下载安装VS2012，之所以用这个版本是因为个人还是很喜欢metro风格的app的，尤其是相比VS2010看上去好看很多。  

在GitHub fork pbrt-v2，然后clone到本地。用VS2012打开src/pbrt.vs2010/pbrt.sln 这个文件。

<span class="label label-success">Windows API</span>  

编译pbrt需要windows api，不过VS2012只有Windows 8 的API支持。不过问题不大： 去[下载](http://www.microsoft.com/en-ca/download/details.aspx?id=8279) Windows SDK 7.1， 安装之后找到安装的文件，将includes和lib文件夹分别添加在pbrt和lib-pbrt两个项目的属性里。也可以通过将这两个path分别添加到__$WindowsSDK_IncludePath__ 和 __$WindowsSDK_LibraryPath_x64__ 两个环境变量中。