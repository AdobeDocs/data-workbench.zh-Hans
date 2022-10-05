---
description: 本节介绍如何为架构设计和实施的Data Workbench数据集创建主键值（跟踪ID）。
title: 数据处理 - 构建主密钥
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# 数据处理 - 构建主密钥{#data-processing-building-primary-key}

{{eol}}

本节介绍如何为架构设计和实施的Data Workbench数据集创建主键值（跟踪ID）。

## 了解跟踪ID {#section-24683031044a4af49988655ccb9a45fd}

在DWB中读取和解码数据（使用解码器）后，第一步是定义跟踪ID和时间戳。 跟踪ID是唯一标识客户记录的标识符。 它可以是动态消息中的任意字段，如电子邮件ID、社交安全号、Cookie ID等。 用作跟踪ID的字段由客户端在发现会话期间决定。 跟踪ID和时间戳是必填字段，必须为每个记录定义。

通常，对于在线数据，Cookie ID( *x_visid_high* 和* x-visid_low*)用作唯一客户标识的默认机制，但可根据客户的要求更改此机制。 发生请求（或事件）的日期和时间为 *x-timestamp*. DWB中的所有记录按 *trackingid* 并按时间戳排序。 必填字段 [!DNL Definitions.cfg] 文件是定义必填字段的日志处理数据集包含文件： *x-trackingid* 和 *x-timestamp*.

注意：*x-trackingid *在DWB中是一个内置字段，此名称不应用于任何其他字段。

**示例1**:创建 *x-trackingid* 使用Cookie ID（仅使用在线数据时）

要在DWB中使用Cookie ID创建*x-trackingid *，请使用哈希函数创建 *x-trackingid* 在 [!DNL foundation.cfg] 文件(在 [!DNL foundation.cfg] 但是，它可以在 [!DNL Dataset > log processing] 文件夹)，如下所示：

![](assets/dwb_impl_primary_key1.png)

**示例2**:创建 *x-trackingid* 使用电子邮件ID（当联机和离线数据均可用时）

假设离线和在线数据均可用（例如，此示例），并且电子邮件ID在两个数据源中均可用。 由于电子邮件ID是唯一标识客户的，因此它将用于创建 *x-trackingid*.

使用Hash函数创建 *trackingId* 如下所示：

![](assets/dwb_impl_primary_key2.png)
