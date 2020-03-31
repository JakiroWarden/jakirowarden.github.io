---
layout:     post
title:      GPU Programming Learning
subtitle:   GPU执行结构
date:       2020-03-29
author:     Jakiro
header-img: img/basicIMG/article_bg_07.jpg
catalog: true
tags:
    - CUDA
    - Computer Graphics
    - 学习
    - GPU Programming
---







#### GPU硬件结构

---

运行CUDA内核的GPU的组成部分包含streaming multiprocessors(SMs)。

<center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://upload-images.jianshu.io/upload_images/1516503-cba59dd5756dc347.png?imageMogr2/auto-orient/strip|imageView2/2/w/426/format/webp">    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">Fermi SM</div> </center>

- CUDA Cores
- Shared Memory/L1 Cache
- Register File
- LD/ST (Load/Store Units)
- SFU (Special Functions Units)
- Warp Scheduler



每个SM支持多个线程并发执行，每个CPU通常有多个CPU。

CUDA采取SIMT（Single Instruction Multiple Threads）体系结构。与CPU使用SIMD（Single Instruction Multiple Data）有所差异。

- SIMT与SIMD本质上都是单指令多数据。SIMT本质上是SIMD的拓展。
- SIMD是数据路径的一种组织形式，相同的指令在不同的数据通道（datapath lanes）上同时被执行。
- SIMT是多线程模型。一个应用被一个程序加载在多线程上，不同的线程动态被动态调度到SIMD datapath上。



Shared Memory依据线程进行划分，不同线程可以通过Shared Memory通信。

逻辑上，一个线程块内所有线程同时执行，物理上，一个线程块内的所有线程不是同时执行的。



#### 相关参考

---

- [CUDA TOOLKIT DOCUMENTATION](https://docs.nvidia.com/cuda/)



