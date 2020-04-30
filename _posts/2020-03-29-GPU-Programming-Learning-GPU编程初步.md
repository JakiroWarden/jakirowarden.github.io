---
layout:     post
title:      GPU Programming Learning
subtitle:   GPU编程初步
date:       2020-03-29
author:     Jakiro
header-img: img/basicIMG/article_bg_08.jpg
catalog: true
tags:
    - CUDA
    - Computer Graphics
    - 学习
    - GPU Programming
---



#### GPU结构

---

##### Core

core是GPU的核心。运算需要数据、ALU和Context。

ALU用于计算数据，Context用于存储结果。

在GPU并行的过程中，一个Core共享一个指令集，有着不同的线程，每个线程有自己的ALU和Context，还有一部分Shared Context是大家共有的。



#### Work Group

---

> wrap(Nvidia), Wavefront(AMD), quad(Work Group)

GPU的运算限制不是由ALU决定的，而是由IO和存储决定的。

由于GPU对于主内存的访问较慢（远远慢于ALU计算所需要的时间）。

同一时间，只有一个Work Group工作。当某个Work Group需要访问主内存或者空闲时，GPU控制切换Work Group。



#### GPU Programming

---

gpu内存：global memory, local memory|registers, shared memroy

- 线程数是32的倍数。



###### sysnc()

- 逻辑上是同步的，但物理上可能不是同步的。

###### if()

- 尽量避免warp分支。



#### 相关参考

---

- [CUDA TOOLKIT DOCUMENTATION](https://docs.nvidia.com/cuda/)



