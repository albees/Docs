# 概述

chrome.net是基于tangram技术实现的chrome扩展应用,它将桌面应用程序和web的优势集成与一体。

为什么选择chromium浏览器来做这个结合？


## chrome浏览器的现状

Google Chrome是Google开发的免费网络浏览器。目前在全世界浏览器市场占有率中是最多的，可以说是目前世界上最好的浏览器。
Chrome代码是基于其他开放源代码软件所编写，包括Apple WebKit和Mozilla Firefox，并开发出称为“V8”的高性能JavaScript引擎。Google Chrome的整体发展目标是提升稳定性、速度和安全性，并创造出简单且有效率的用户界面[。CNET旗下的Download.com网站评出的2008年6月最佳Windows应用程序，其中Google Chrome排名首位。

据StatCounter统计，截至2018年第一季度，Google Chrome在全球桌面浏览器的网页浏览器的使用分布为66%。

截至2018年8月，全球浏览器市场份额排名如下：


|排名|推荐|比重|
|---|-|---|
| 1 |谷歌的Chrome浏览器| 67.63％|
| 2 | Mozilla Firefoxr | 10.97％|
| 3 |微软的IE浏览器| 7.02％|
| 4 | Apple的Safari浏览器| 5.13％|
| 5 | Microsoft的Edge浏览器| 4.24％|
| 6 | Opera浏览器| 2.48％|

## chrome.net

Chrome的相应开源项目称为Chromium，Chromium作为Google的一个巨大项目，有超过10 GB的源代码。 经过10年的发展，Chromium并不是一个纯粹的网络浏览器项目。它提供了多种扩展机制，包括标准Chrome扩展，Native Messaging，WebAssembly。 一些衍生项目包括CEF和Electron。 它用于创建更多创意应用程序。 Web和Local之间的界限逐渐被打破。

而我们的chrome.net就是桌面应用和chrome优势的一种集成。chrome.net的目标以chrome为范例，利用tangram技术，为大家展示如何将web与原生桌面应用相结合，提供一种web与原生桌面元素相结合的技术，使web技术可以和原生桌面元素进行多元化组合。

chrome.net目前可以实现以下效果：
图图图

- 支持从图形界面角度扩展chrome，可将chrome原网页扩展为多种样式，如下图：各种格的图
- 在chrome窗口中支持加载.net组件
- 支持.net组件和chrome之间数据交互

在以下部分中，我们将介绍如何使用tangram扩展Chromium。如果您只想体验效果并且不想花时间编译Chromium（大约需要2-3天），那么您可以从我们的网站下载我们的预编译分发包（这地方给链接）。

# 准备工作
## 系统要求
由于chromium源码超过10GB，是一个巨大的项目，80%的人可能都没见过如此大胆的项目，通常来说，在vs中加载四五十个工程文件就已经很大了，但chromium源代码有六千多个工程，几乎是无法阅读的。面对如此庞大的项目，硬件资源是一个大问题，如果没有足够的硬件资源，那么要花费您很长的时间进行编译。为此我们结合自己在此工作过程中的经验建议下面的几种硬件配置。
1. 个人开发最低配置
1台电脑，配置如下：
- 64位Intel机器，至少8GB RAM。 强烈推荐超过16GB
- c盘至少有600G的空间
- 适当版本的Visual Studio
- Windows 10

2. 个人开发的合理配置：
2台机器，1台用于更新chromium源码，1台用于工作，两台交替工作。每台配置都如下所述：
- 64位Intel机器，至少16GB RAM，最好32GB 
- 高速硬盘，容量至少1T 
- 适当版本的Visual Studio
- Windows 10
           
3. 一个6人团队开发的合理配置：
- 4台服务器 
- 6台个人电脑 
- 每台配置都如2所述 
       
## 开发环境
  
### Visual Studio 2017
- add .NET desktop development
   - add Visual C++ ATL for x86 and x64
   - add Visual C++ MFC for x86 and x64
   - add C++/CLI support
- add Desktop development with C++
- add Visual Studio extension development
- add Microsoft.VisualStudio.Component.VC.140

### depot_tools
### Python 2.7 for Windows
### Git for Windows
### 网络代理配置
若您所在地区无法连接chromium源码地址，则需要提前处理网络代理问题，若您不想处理此部分，中国区用户可从连接地址获取chromium源码。

### 特别提示
由于chromium源码的体积太大，首次下载源码和编译都需要很长的时间（一般配置的话在20小时左右），建议大家将下载和编译都放在晚上睡觉前或周末不用电脑时进行。

下面是我们在工作中不同设备的时长统计，供大家参考.

|设备名|配置|编译所用时长|
|---|-|---|
|联想台式机|Inter Core i5-3470 CPU;8G RAM; 64-bit system; NTFS-formatted hard drive 1T|22h|
|Surface Book 2|8代酷睿 i7/16GB/1TB/GTX 1060 6GB|16h|
|Dell PowerEdge R710 rack server|16 CPU cores, 128GB of memory, and six 16,000-rpm mechanical hard drives|15h|

# 开始扩展
- [chromium](https://chromium.googlesource.com/chromium/src.git)
   - Fetches code via `depot_tools`.
   - sets the branch for Chromium (ex: 70.0.3538.77).
- [tangram](https://github.com/tangarm/Tangram)
   - Mounted at `src\tangram`.
- 
   


