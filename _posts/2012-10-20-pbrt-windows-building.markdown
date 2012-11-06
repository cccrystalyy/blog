---
title: Building pbrt with VS2012
layout: post
guid: urn:uuid:silentlistener-2012-10-20-1958
tags:
  - pbrt
  - C++
  - Graphic
  - VS2012
  - RayTracing
lastUpDate: 2012.10.30
---
##Preparation
首先下载安装VS2012，之所以用这个版本是因为个人还是很喜欢metro风格的app的，尤其是相比VS2010看上去好看很多。  
在GitHub fork pbrt-v2，然后clone到本地。用VS2012打开src/pbrt.vs2010/pbrt.sln 这个文件。打开以后会提示升级项目文件，点击ok即可。  


##Windows API
编译pbrt需要windows api，不过VS2012只有Windows 8 的API支持。不过问题不大： 去[下载](http://www.microsoft.com/en-ca/download/details.aspx?id=8279) Windows SDK 7.1， 安装之后找到安装的文件，将includes和lib文件夹分别添加在pbrt和lib-pbrt两个项目的属性里。也可以通过将这两个path分别添加到__$WindowsSDK_IncludePath__ 和 __$WindowsSDK_LibraryPath_x64__ 两个环境变量中。   

<span class="label label-warning">注意</span>: windows api里也有个文件叫做parser.cpp 和pbrt里的parser.cpp同名，所以需要将windows api的path 放在最后，这样编译的时候就会优先使用pbrt的api。

##Bison&Flex 
这两个是将yacc和lex编译成C语言文件的工具(词义和语法分析工具)。虽然说明上说如果你不修改pbrt parser的话不需要安装这个部分，但是实际上没有这个是无法编译libpbrt的。安装很简单，下载链接在这里: [Bison](http://gnuwin32.sourceforge.net/packages/bison.htm), [Flex](http://gnuwin32.sourceforge.net/packages/flex.htm).不过要注意安装路径的选择:
>Do not install under "Program Files" or "Program Files (x86)". The installation path should not contain any spaces. Use C:\cygwin or C:\gnuwin32, for example.

##Running&Debugging
Build完成之后，会在bin文件夹里生成pbrt.exe. 要渲染一个场景,打开power shell输入:
> cd PathToPbrt  
  .\bin\pbrt.exe .\scenses\bunny.pbrt

<span class="label label-warning">注意</span>: 使用VS2012 Debugging时要注意路径问题，VS处理反斜杠有点点问题，所以我修改了属性里的debugging 设定。
![VS2012PBRT](http://i.imgur.com/sAotK.png)


> PS: 渲染程序的入口在 api.cpp的1142行，当yyparser检测到World End的时候。