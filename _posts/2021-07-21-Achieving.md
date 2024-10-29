---
layout: post
title: Achieve a small goal
tags: [collection]
---

以双曲树形式浏览文件夹的结构，并且为每个节点建立文件链接，可以直接打开

2 年之前找到 treeviz 的 java 程序，第一次在电脑上装上 JRE。但是这个程序的作者 2003 年之后就不再更新了，软件基本符合要求，但是字体在 1080p 的屏幕上非常小。届时，我在网上找到的解决方法都是修改 javaw.exe 文件随系统缩放的属性，问题不在这里，所以自然不起作用。束手无策的一个瞬间。

期间，我也多次花时间找新出的软件中是否有完善的基于其他语言的，试过 treeview browser，tag space 等等，都比较失望，它们的双曲图不够灵活好看。另外，发现 jar 文件本质是打包后，也试过一些可以 edit jar 的软件（eclipse，vim），奈何我对 java 没有一丁点的概念，都失败告终。

今天心血来潮，再一次发起冲击。用 VS code 打开 project，运行 java 主程序，我看到了生成的窗口。搜索字体，发现 SwingHTView 为名的文件，控制双曲图的界面，修改字体大小。而修改字体需要在 jre/lib/fonts/fallback/拖入想要的字体的 ttf，才能在程序中引用。紧接着，发现 swing 的字体渲染非常糟糕，我也不知道抗锯齿的指令要加到哪里才能生效。就暂时没有办法。

VS code 打包 jar 文件，在这里我花了很多时间，一直试，一直出错。心酸不说了。最终导出可以运行的 jar： ctrl+shift+P ——> export: jar ——> proceed ——> main ——> only bin, ok. 到此为止我导出的 jar 还是正常的，只有在 jdk 中才能运行，而原作者打包的版本在 jre 中就能运行了。jre 的字体渲染比 jdk 好一些（why？）。未完待续……

java 中新的结构太多了，代码阅读起来也很吃力。太难了。