---
title: Bugtags使用感触
date: 2015-12-18 23:22
updated: 2015-12-19 01:34
tags: 
  - Bug管理
  - Bugtags
excerpt: 写在Bugtags上线Crash发生趋势之际，以及英语四级前夜。仅感触，无其他。
categories: Bugtags
permalink: 201512-bugtags-feedback.html
author: admin
toc: true
---

# 0x01	前言、
写在Bugtags上线Crash发生趋势之际，以及英语四级前夜。仅感触，无其他。
# 0x02	起缘、
在9月份的时候，开学之际，随着Codekk微信号推送了一条名为“移动应用Bug快速反馈利器”的消息，工欲善其事，必先利其器。看完介绍了以后，不禁感觉眼前一亮，和以前接触的crash收集工具有点不一样，并且也听说过一些摇一摇进行反馈的功能。

这个主要是一个类似于外包的项目，应用内容是大学内app社交、社区等形式，其中整体APP需要一个良好的架构，以及完善的测试（然而并没有测试），只好在边开发边测试。

最初我们在应用开发上，采用的git版本控制，主要两个人进行开发，并没有测试妹纸。（最初找了一个“设计师”同学），在经理提出项目需求和改进时，往往通过经理去告诉给另外一个人，然后另一个人进行评估，直接在代码里进行修改，并且没有记录，整个过程并不透明。后来经理会找张纸记录一些问题，解决了打个对勾，但是这还是不好管理，并且对于机型的不确定性，以及Bug的难复现，降低了一些效率。

此处应该有图片：

<img class="responsive-img" src="https://dubuqingfeng.oss-cn-hongkong.aliyuncs.com/blog/tech/blog201512-bugtags-feedback-01.jpg">

在公众号信息里，展示了提交Bug的流程，然后试着集成了一下sdk，整体集成的过程并不麻烦，很快感受到了效果，并推荐给了另一位开发。

在接入以后，熟悉了提交Bug的方式，感觉相见恨晚，很适合经理在提哪有问题，哪需要改进。

# 0x03	成长、
在接入应用以后，效率上感觉到了一些方便，但是就发现了一些问题，比如那会会一直邮件收到提醒，并提了工单，在QQ群里也进行了咨询，并且收到了这个问题正在解决中，会在下周上线。

并且Bugtags提交Bug时，整体流程并不麻烦。

令人感到欣慰的是，Bugtags团队的迭代，使得Bugtags不断的完善，随着使用中，逐渐上线了以下几个特性：

> 增加几种标签状态和类型。
> 
> 区别了开发人员和提交Bug人员
> 
> 可以批量修改状态和删除标签
> 
> Crash可以抓到截图
> 
> 支持了导出功能
> 
> 增加匿名提交
> 
> 添加了批量邀请成员等功能
> 
> ……

在团队的不断迭代开发应用的过程中，收到了很多经理的提的标签，经常一天提十几条，如果按照往常的列出清单，然后一个一个去解决，会浪费很多时间和效率。

应用也在fir.im内测，不断的去完善，提高着自己的开发技能，奔溃影响机型数从最初的少量的几台手机在逐渐增加。

此处应该有图片：

<img class="responsive-img" src="https://dubuqingfeng.oss-cn-hongkong.aliyuncs.com/blog/tech/blog201512-bugtags-feedback-02.jpg">

# 0x04	伴随、
在使用的过程中，提交的问题越来越多，收到的标签也越来越多，毕竟是一个APP应用，从0.1到0.9的过程（0.1指接入时已经开发了一个简单原型）。

一张现在的统计，标签已经不少了，此处继续应该有图片：

<img class="responsive-img" src="https://dubuqingfeng.oss-cn-hongkong.aliyuncs.com/blog/tech/blog201512-bugtags-feedback-03.jpg">

问题界面：

<img class="responsive-img" src="https://dubuqingfeng.oss-cn-hongkong.aliyuncs.com/blog/tech/blog201512-bugtags-feedback-04.jpg">

随着不断的使用，发觉提高了不少效率，在这将近三个月的相处之中，感受到了Bugtags团队的不懈努力，感受到了对开发与测试的关注。

并且现在也提供了一些可视化的数据，来表达测试的效果，以及应用的完善程度。

在上线以后，我们也重点关注了一些Crash，并且Crash相对于以前来说，更加好复现，并且对其进行了改进，优化应用的性能，提升了一些用户体验。

因为机型和系统不同，作为一个android开发者，不可避免地会遇到很多Crash，当用户遇到了以后，作为开发也很无奈，毕竟比较难复现，有了Bugtags了以后，可以及时地统计机型，系统版本，以及用户所执行的步骤，现在最近又上线了Crash的发生趋势，可以让开发专注于近期发生频率高的Crash进行改进。

此处应该有图片：

<img class="responsive-img" src="https://dubuqingfeng.oss-cn-hongkong.aliyuncs.com/blog/tech/blog201512-bugtags-feedback-05.jpg">

在今年的华北五省计算机应用大赛的答辩现场，也给评委们简单介绍了一下这个 Bug 管理平台，提高了一些开发效率。

# 0x05	后记、

你们的测试妹子、霸道产品、老板肯定需要它很久了，爱他恨他就转给他。

在Bugtags之前，并不知道有相关的Bug管理平台，作为一名开发者，Bugtags是值得推荐的。

最后提几点意见（其中有些不知道中肯与否）：

> 开发android studio插件，实现可以收到紧急标签会提醒。
> 
> 开发android客户端，实现可以移动管理标签状态。
> 
> 开放一些api，实现自定义配置
> 
> 希望可以提供一些移动应用测试，例如monkey之类的实践。
> 
> 如果是非Wi-Fi环境下，提供一些流量方面的统计。
