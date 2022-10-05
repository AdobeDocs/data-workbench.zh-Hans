---
description: 本节介绍Saint Scrubber脚本。
title: 编写 SAINT Scrubber 脚本
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
exl-id: 5f6d92b1-baaa-4d67-a1c2-ce7d51affb17
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 1%

---

# 编写 SAINT Scrubber 脚本{#scripting-for-the-saint-scrubber}

{{eol}}

本节介绍Saint Scrubber脚本。

## SAINT分类概述 {#section-b840a99f10684bb4b58e844a515d0d79}

SiteCatalyst属性导入和命名工具的首字母缩略词SAINT也知道分类。

当我们对SiteCatalyst变量进行“分类”时，即表示您正在变量与与该变量相关的元数据之间建立关系。 分类在“促销活动”区域中最常用，因此我将使用它来解释它们。 大多数客户使用跟踪代码将促销活动流量发送到其网站。 此跟踪代码是一个标识符，可能表示在Google上购买的特定关键词，如“goog123”。 此标识符会传递到s.campaigns变量中，以便您能够查看访客从该促销活动代码访问您的网站后发生的网站成功事件。

但是，如果您想要按搜索引擎、关键词或促销活动渠道来查看促销活动结果，而不是仅通过跟踪代码查看促销活动，该怎么办？ 您是否必须为搜索引擎创建新的转化变量、关键词的转化变量以及促销活动渠道的转化变量？ 如果是，则仅营销活动中会使用50个变量中的许多变量！ 谢天谢地，您可以使用“分类”功能，让您的生活更轻松！ 由于每个跟踪代码可以具有搜索引擎、关键词或促销活动渠道，因此您只需为促销活动变量创建三个分类来表示每个变量。 您实质上是在告诉SiteCatalyst，促销活动变量与这三个其他“元数据”值之间存在直接关系。 通过执行此操作，SiteCatalyst将允许您根据所有四个变量对网站成功事件进行细分，而无需额外标记。

## SAINT在DWB中的擦洗脚本 {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

当您将任何SAINT分类数据引入DWB时，会使用此脚本。 脚本 *SaintScrubber.dat* 通常位于 *\Scripts\Scripository* 文件夹。

此脚本的主要用途是删除 `<discoiqbr>` SAINT分类文件。 此外，如果列标题行中提及的列检查所有数据行，则它会计算该数字。 如果有列数少于或大于多于的行，则会从文件中删除这些行。

的 *SaintScrubber.dat* 内部调用*saint_scrubber.pl *script。 以下是此脚本文件的详细信息：

路径： *E:\Scripts\Scripository\Library\Perl*

脚本参数：

1. 输入文件夹（必填）：source_directory
1. 输出文件夹（必填）：destination_directory
1. 分隔符（必填）：分隔符
1. 拒绝文件夹（可选）（参数可留空或在命令行中忽略）
1. 日志文件夹（可选）（参数可留空或在命令行中忽略）

在Perl脚本中执行的步骤：

1. 将转义表单馈送、换行符、回车符、制表符替换为空格。
1. 删除在UTF-8 BMP（基本多语言平面）中解释为控制字符的双字节，以下情况除外：

   * 9水平选项卡
   * 10行馈送
   * 12个表单馈送
   * 13回车
   * 使用管道关键字作为 |例如：分隔符管
   * 删除其他麻烦的字符
   * 在上述推移之后，删除与第一个数据行具有不同列数的任何行（不为空或注释）
   * 支持可选的拒绝文件以保存被拒绝的行，而不是只跳过它们
   * 支持递归输入文件夹；生成同一结构的输出文件夹
   * 将已处理的输入文件移动到已处理的子文件夹，以便脚本在同一现有输入文件夹上再次运行时不会重复该操作
   * 识别Workbench文件名中的日期；先按日期，再按字母对处理进行排序 — 无论文件夹名称如何。 这将确保无论Workbench文件类型（ecom、非ecom）或报表包ID（如果您将多个报表包处理到单个Insight数据集中）如何，序列都是正确的。
   * 支持电子邮件警报 `<discoiqbr>`
