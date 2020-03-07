---
description: 本部分是一个快速指南，其中提供了设置和计划脚本以每周重新处理日志文件所需的最少步骤。 这可用作设置或修改配置文件的参考指南。
title: 脚本编写到每周重新处理
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 脚本编写到每周重新处理{#scripting-to-weekly-reprocess}

本部分是一个快速指南，其中提供了设置和计划脚本以每周重新处理日志文件所需的最少步骤。 这可用作设置或修改配置文件的参考指南。

## 什么是重新处理 {#section-7e335aacc199488592e78a835e2649fe}

根据数据源、脱机数据源或时间段的更改将数据加载到DWB。 该脚本将重新处理 *Log Processing.cfg文件中的开始日期参数* 。

## 先决条件 {#section-804acce5df4942469c9313535627038a}

报表包ID、DWB中应提供的月数数据。 Perl64文件夹应在C:\ drive文件夹中可用。

## 重新处理日志 {#section-565d3e1f0df14127a97d9beecd14f02f}

在Windows命令脚本 *Reprocess.bat中提供上述详细信息（前提条件）* ，该文件夹位于 *\scripts\Log Processing主FSU服务器上* 。

此脚本将在内部调用两个特定于客户端的脚本：一个用于重新处理数据，另一个用于发送电子邮件警报。 这两个脚本也位于\scripts\Log Processing文件夹 *中* 。

该脚本将更改 *Log Processing.cfg文件中的重新处理参数* 。

## 日志滚动窗口 {#section-ed5f44d890b34523ab33da7aa0ae3990}

在Windows命令脚本logprocessingdate.bat中提供详细信息( *先决条件)* ，该文件夹位于 *FSU服务器上的\scripts\Scripository* 。 此脚本将在内部调用两个特定于客户端的脚本：一个用于设置日志的开始日期，另一个用于发送电子邮件警报。 这两个脚本也可在* \scripts\Scripository*中找到

在* logprocessingdate.bat*文件中提供报表包ID和月数。

该脚本将更改 *Log Processing.cfg中的开始日期参数*。

>[!NOTE]
>
>如果“ *Scripository* ”文件夹不可用，请按照以下过程复制“ *Scripository* ”文件夹，并使用特定于客户的详细信息在上述文件中进行更改。 并提供您的电子邮件地址以在出现任何错误时获得警报。

## 计划脚本 {#section-063cf0c755dc47d28d60947d8d43d0e9}

按照以下步骤在Windows任务调度程序中调度脚本。

1. 在Windows的任务调度程序中调度脚本。

   * 打开任务调度程序：右键单击任务调度 **程序库** ，然后单击 **创建任务**。

   * 在“常规 **** ”选项卡中，提供任务名称并选择“ **选项”**。

   * 在“触 **发器** ”选项卡下，单 **击“新建** ”，此时将打开新窗口。

   * 在“操 **作** ”选项卡下，单 **击“新建** ”(New)，将打开新窗口。 然后提供脚本详细信息和其他选项。 （开始将有一个放置脚本的路径）。

1. 验证：右键单击并运行作业，验证 *Log processing.cfg文件中的更改* 。 将向脚本中提供的电子邮件ID发送电子邮件。

