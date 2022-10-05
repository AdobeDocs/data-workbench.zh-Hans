---
description: 有关解决Web服务器问题的信息，例如，如果Web服务器不旋转，或者Web服务器出现故障。
title: 了解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# 了解原因{#understanding-the-causes}

{{eol}}

有关解决Web服务器问题的信息，例如，如果Web服务器不旋转，或者Web服务器出现故障。

## 当Web服务器取消旋转时 {#section-b9f709099cb44b4f9d1acb38ca5330e3}

当Web服务器从服务器池中取出轮替，但与发送周期性心率的发送器连接时，开始时间保持为最新，无需任何人干预。

## Web服务器失败时 {#section-19280cf83ca44bd7b1ee11bfc74494d2}

当Web服务器由于某些灾难性故障而完全离线，或者未发送数据或心率时， [!DNL data workbench server] 来保证它代表 [!DNL data workbench server] 从其感知的所有数据源接收数据。 系统本身将继续处理数据，该数据仍可用于Data Workbench分析，但 [!DNL data workbench server] 基于截止时间的数据将不起作用。 例如，“截止时间”会触发报表，用于在系统中创建许多派生维度。 停止“截止时间”时，不会触发报表，并且这些特定的派生维度不可用。

例如，如果WEB2在6月15日离线，并且有5天没有发送任何数据，则截止时间将在6月15日的某个时候。 例如，“昨天”的维度将为6月14日，即使今天的日期是6月20日。
