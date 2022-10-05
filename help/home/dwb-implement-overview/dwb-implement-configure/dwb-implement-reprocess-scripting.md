---
description: 本部分是一个快速指南，其中提供了设置和计划脚本以每周重新处理日志文件所需的最低步骤。 这可用作设置或修改用户档案的参考指南。
title: 编写每周重新处理的脚本
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# 编写每周重新处理的脚本{#scripting-to-weekly-reprocess}

{{eol}}

本部分是一个快速指南，其中提供了设置和计划脚本以每周重新处理日志文件所需的最低步骤。 这可用作设置或修改用户档案的参考指南。

## 什么是重新处理 {#section-7e335aacc199488592e78a835e2649fe}

根据数据源、离线数据源或时间段的更改将数据加载到DWB。 脚本将在 *Log Processing.cfg* 文件。

## 前提条件 {#section-804acce5df4942469c9313535627038a}

报表包ID，DWB中应提供的月数数据。 Perl64文件夹应可在您的C:\ drive文件夹中找到。

## 重新处理日志 {#section-565d3e1f0df14127a97d9beecd14f02f}

在windows命令脚本中提供上述详细信息（先决条件） *Reprocess.bat* 可在文件夹中找到 *\scripts\日志处理* 在主FSU服务器上。

此脚本将在内部调用两个特定于客户端的脚本：一个用于重新处理数据，另一个用于发送电子邮件警报。 这两个脚本在 *\scripts\日志处理* 文件夹。

脚本将更改 *Log Processing.cfg* 文件。

## 日志滚动窗口 {#section-ed5f44d890b34523ab33da7aa0ae3990}

在windows命令脚本中提供详细信息（先决条件） *logprocessingdate.bat* 可在文件夹中找到 *\scripts\存储库* 在FSU服务器上。 此脚本将在内部调用两个特定于客户端的脚本：一个用于设置日志的开始日期，另一个用于电子邮件警报。 这两个脚本在* \scripts\Scripository*中也可用

在* logprocessingdate.bat*文件中提供报表包ID和月数。

脚本将在 *Log Processing.cfg*.

>[!NOTE]
>
>如果 *存储库* 文件夹不可用，请按照以下流程复制 *存储库* 文件夹，并使用特定于客户的详细信息在上述文件中进行更改。 并提供您的电子邮件地址，以便在发生任何错误时获取警报。

## 计划脚本 {#section-063cf0c755dc47d28d60947d8d43d0e9}

请按照以下步骤在Windows任务计划程序中计划脚本。

1. 在Windows任务计划程序中计划脚本。

   * 打开任务调度程序：右键单击 **任务调度程序库** 单击 **创建任务**.

   * 在 **常规** 选项卡，提供任务名称并选择 **选项**.

   * 在 **触发器** ，单击 **新建** 新窗子会打开。

   * 在 **操作** ，单击 **新建** 新窗子会打开。 然后，提供脚本详细信息和其他选项。 （开始时将有一个放置脚本的路径）。

1. 验证：右键单击并运行作业，并验证 *Log processing.cfg* 文件。 将向脚本中提供的电子邮件ID发送电子邮件。
