---
description: 有关解决Web服务器问题的信息，例如，如果Web服务器不旋转，或者Web服务器出现故障。
title: 了解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# 了解原因{#understanding-the-causes}

有关解决Web服务器问题的信息，例如，如果Web服务器不旋转，或者Web服务器出现故障。

## 当Web服务器不旋转{#section-b9f709099cb44b4f9d1acb38ca5330e3}

当Web服务器从服务器池中取出轮替，但与发送周期性心率的发送器连接时，开始时间保持为最新，无需任何人干预。

## 当Web服务器失败{#section-19280cf83ca44bd7b1ee11bfc74494d2}时

当Web服务器因某些灾难性故障而完全脱机，或者未发送数据或心率时， [!DNL data workbench server]上的截止时间将停止，以确保它表示[!DNL data workbench server]上次从其感知的所有数据源接收数据的时间。 系统本身将继续处理数据，该数据仍可在Data Workbench中进行分析，但[!DNL data workbench server]中任何基于“截止时间”的数据都不起作用。 例如，“截止时间”会触发报表，用于在系统中创建许多派生维度。 停止“截止时间”时，不会触发报表，并且这些特定的派生维度不可用。

例如，如果WEB2在6月15日离线，并且有5天没有发送任何数据，则截止时间将在6月15日的某个时候。 例如，“昨天”的维度将为6月14日，即使今天的日期是6月20日。
