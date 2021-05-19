---
layout: post
title:  "声波命令注入"
date:   2021-05-12 10:25:45 +0000
categories: jekyll update
description: 声波命令注入
---

## 555 产生方波脉冲

555 电路图：

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/VoiceAttack/555.png)

产生的方波脉冲：

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/VoiceAttack/20.png)

通过调节 RA， RB 和电容 C 可以调节 555 模块的脉冲占空比和频率

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/VoiceAttack/50.png)

## 超声波模块

当大量超声波模块组成阵列后， 发出的调频声音信号会在空气中自解调， 使声音信号能被听到。

声音信号只有在超声模块阵列的前方才能被明显听到， 在其他地方基本听不到。

## 原理

通过 555 模块产生 40 KHz 的方波脉冲， 然后把音频信号加入到 555 模块的第 5 管脚， 改变 555 模块产生方波脉冲的频率， 产生调频信号。

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/VoiceAttack/signal.png)

## 完成的工作

调节 RA， RB 和 C ， 使得 555 模块产生的方波接近 50% 占空比， 并且频率接近 40KHz。

最终产生的声音信号能够被音响所识别。
