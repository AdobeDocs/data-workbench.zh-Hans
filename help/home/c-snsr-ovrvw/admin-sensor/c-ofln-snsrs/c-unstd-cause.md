---
description: 有关解决Web服务器问题的信息，例如，如果Web服务器取消旋转，或Web服务器发生故障。
title: 了解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# 了解原因{#understanding-the-causes}

有关解决Web服务器问题的信息，例如，如果Web服务器取消旋转，或Web服务器发生故障。

## 当Web服务器退出旋转{#section-b9f709099cb44b4f9d1acb38ca5330e3}

当Web服务器从服务器池中取出旋转，但与发送周期性心跳的发送器连接时，“开始时间”保持最新，不需要对任何人进行干预。

## 当Web服务器发生{#section-19280cf83ca44bd7b1ee11bfc74494d2}故障时

当Web服务器因某些灾难性故障而完全离线，或者未发送数据或心跳时， [!DNL data workbench server]上的“截止时间”将停止，以确保它代表从其所知的所有数据源中接收到的[!DNL data workbench server]数据的最后一次时间。 系统本身继续处理数据，但[!DNL data workbench server]中基于“开始时间”的任何内容都不起作用。 例如，“开始时间”触发报告，用于在系统中创建许多派生维。 当“截止时间”(As Of)停止时，不会触发报告，这些特定派生维度不可用。

例如，如果WEB2在6月15日脱机并且在五天内未发送任何数据，则截止时间将在6月15日的某个时候。 例如，“昨天”的维度将是6月14日，尽管今天的日期是6月20日。
