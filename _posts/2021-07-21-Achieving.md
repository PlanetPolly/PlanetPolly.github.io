---
layout: post
title: Achieve a small goal
tags: [collection]
---

以双曲树形式浏览文件夹的结构，并且为每个节点建立文件链接，可以直接打开

2年之前找到treeviz的java程序，第一次在电脑上装上JRE。但是这个程序的作者2003年之后就不再更新了，软件基本符合要求，但是字体在1080p的屏幕上非常小。届时，我在网上找到的解决方法都是修改javaw.exe文件随系统缩放的属性，问题不在这里，所以自然不起作用。束手无策的一个瞬间。

期间，我也多次花时间找新出的软件中是否有完善的基于其他语言的，试过treeview browser，tag space等等，都比较失望，它们的双曲图不够灵活好看。另外，发现jar文件本质是打包后，也试过一些可以edit jar的软件（eclipse，vim），奈何我对java没有一丁点的概念，都失败告终。

今天心血来潮，再一次发起冲击。用VS code打开project，运行java主程序，我看到了生成的窗口。搜索字体，发现SwingHTView为名的文件，控制双曲图的界面，修改字体大小。而修改字体需要在jre/lib/fonts/fallback/拖入想要的字体的ttf，才能在程序中引用。紧接着，发现swing的字体渲染非常糟糕，我也不知道抗锯齿的指令要加到哪里才能生效。就暂时没有办法。

VS code打包jar文件，在这里我花了很多时间，一直试，一直出错。心酸不说了。最终导出可以运行的jar： ctrl+shift+P ——> export: jar ——> proceed ——> main ——> only bin, ok. 到此为止我导出的jar还是正常的，只有在jdk中才能运行，而原作者打包的版本在jre中就能运行了。jre的字体渲染比jdk好一些（why？）。未完待续……

java中新的结构太多了，代码阅读起来也很吃力。太难了。