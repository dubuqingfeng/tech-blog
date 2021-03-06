---
title: 基于 Arduino 的解魔方机器人组装调试
date: 2015-03-24 14:23
updated: 2015-03-24 22:12
tags: 
  - 电子设计
  - 解魔方机器人
excerpt: 本文在机械与电路部分的初步设计之下，进行一些主控板与硬件器件的辨析、连接与调试。
categories: 电子设计
permalink: 201503-Rubik's-Cube-Robot-Zhuzhuangtiaoshi.html
author: admin
---

# 0x01 LM3S615
此板是属于TI公司LM3S系列，是ARM Cortex-M3内核，相关手册以及电路图、说明书也在[](http://download)有下载，主要使用20针JTAG接口与J-LINK仿真器进行连接调试，主要有关系的是LM3S615的串口通信，PWM模块和GPIO接口。

# 0x02 TTL与RS-232
波特率
# 0x03 GPIO
第一次接触GPIO是在树莓派上，可以利用其进行一些输入或者输出的控制。

# 0x04 舵机控制板
采用的是普通Arduino24路舵机控制板V4.21，可以通过单片机、Arduino、蓝牙模块等控制舵机。详细说明在[]()。

舵机控制板如图所示，电源，中间可以使用蓝牙模块进行控制，预留了RXD、TXD、GND以及3.3V或5V

# 0x05 UART串口

# 0x06 系统控制框图
因为甘特图markdown解析器可能不支持，系统控制框图如图所示。

# 0x06 整体结构设计
# #0x07 机械手的设计
CAD截面图如图所示，使用亚克力板进行切割制作
# 0x08 主舵机导轨的设计
# 0x09 从舵机的处理
# 0x10 舵机控制板与舵机的测试
舵机控制板首先需要考虑电源供电的问题，因为舵机电源需要5V的，是否共地，以及舵机的电流等。

舵机部分供电采取DC直流5V，

舵机控制板，先采取笔记本电脑使用usb转串口模块连接，然后利用一些上位机程序，控制舵机的一定角度的旋转，

舵机控制板的一些指令集：
# 0x11 蓝牙与舵机控制板的连接测试
首先需要考虑蓝牙模块供电问题，
# 0x100 参考文献
《ARM体系结构与外设接口实战开发》(北京航空航天大学出版社)
