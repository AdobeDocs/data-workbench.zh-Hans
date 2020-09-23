---
description: 有关解决Web服务器问题的信息，例如，如果Web服务器被取出轮替，或者Web服务器出现故障。
solution: Analytics
title: 了解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---


# 了解原因{#understanding-the-causes}

有关解决Web服务器问题的信息，例如，如果Web服务器被取出轮替，或者Web服务器出现故障。

## 当Web服务器取消旋转时 {#section-b9f709099cb44b4f9d1acb38ca5330e3}

当Web服务器从服务器池中取出旋转，但与发送周期性心跳的发射器连接时，开始时间保持最新，无需任何人干预。

## 当Web服务器发生故障时 {#section-19280cf83ca44bd7b1ee11bfc74494d2}

当Web服务器由于某种灾难性故障而完全离线，或者没有发送数据或心跳时，停 [!DNL data workbench server] 止“截止时间” ，以确保它代表从其所知的所有数据源 [!DNL data workbench server] 中接收到的最后一次数据。 系统本身继续处理数据，Data Workbench中仍可分析，但基于“开始时间”的 [!DNL data workbench server] 任何数据都无法正常工作。 例如，“开始时间”(As Of)时间触发报告，用于在系统中创建许多派生维。 当“开始时间”停止时，不会触发报告，并且这些特定派生维不可用。

例如，如果WEB2在6月15日脱机，并且五天内没有发送任何数据，则截止时间将在6月15日的某个时候。 例如，“昨天”的维度将是6月14日，尽管今天的日期是6月20日。
