---
layout: post
title:  "侧信道功耗分析"
date:   2021-05-10 18:25:45 +0000
categories: jekyll update
description: 侧信道功耗分析
---

## 原理

芯片在判断一个密钥是否为正确密钥时，会运行特定程序，即特定指令。

密钥正确时运行的指令和错误时运行的指令是不一样的。

好比一个程序，用多个 `if else` 判断密钥字符串是否正确， 如果全部正确的话应该会把所有的 `if else` 全部跑完， 如果错误的话应该只有部分指令被执行。

然而芯片在执行不同指令时的功耗会有微小差异， 即电压 Vcc 会有微小差异。

于是可以检测芯片的电压引脚， 观察其功耗变化， 判断密钥是否正确

## 工具

CW1173 (这是一块很完善的芯片， 用 Xilinx 的 FPGA 写成， 并且有配套的 PC 端软件， 但是这玩意儿太贵了， 而且采样率远不如示波器， 所以还不如用示波器)

示波器

## 分析

首先用示波器采集数据， 灯泡在收到关灯指令时的电压变化：

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/side_channel/data.png)

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/side_channel/fft_result.png)

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/side_channel/filter.png)

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/side_channel/filter_result.png)