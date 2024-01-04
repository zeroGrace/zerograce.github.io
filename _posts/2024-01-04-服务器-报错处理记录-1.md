---
layout: post
title:  服务器-报错处理-segmentation_fault
date:   2024-01-04
categories: server
tag: error
---

* content
{:toc}


## 问题描述

运行代码过程中突发报错`segmentation fault(core dumped)`，且每次报错随机，使用者、运行的代码均不相同；继续使用一段时间后（大约30min内）系统突然卡死，远程连接断开且无法再连接，桌面鼠标无法操作；键盘`ctrl+alt+F1`切入tty文字界面后显示下图所示信息，而后彻底无法操作（有时无法切入tty即彻底卡死）

![segmentation_fault](/styles/images/pics/segmentation_fault.png)

![connect_fail](/styles/images/pics/connect_fail.jpg)

![tty-info](/styles/images/pics/tty.jpg)



## 解决方案

排查过程：

1. 代码自身问题：排除，在其他机器上可正常运行；
   
2. 代码运行时CPU负荷过高导致卡死：排除；htop监控CPU使用情况，占用未满时一样会出现上述问题；
   
3. 内存测试：利用MemTest86工具检查内存（参考教程[link](https://blog.csdn.net/qq1327798176/article/details/104156361)）

最终问题为内存硬件问题，在多组test下均出现大量红色报错，联系厂家更换内存条。

![memory_test](/styles/images/pics/memory_test.jpg)
