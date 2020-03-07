---
description: 有关解决Web服务器问题的信息，例如，如果Web服务器取消轮替，或者Web服务器出现故障。
solution: Insight
title: 了解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解原因{#understanding-the-causes}

有关解决Web服务器问题的信息，例如，如果Web服务器取消轮替，或者Web服务器出现故障。

## 当Web服务器取消旋转时 {#section-b9f709099cb44b4f9d1acb38ca5330e3}

当Web服务器从服务器池中取出旋转，但与发送周期性心跳的发射机连接时，“开始时间”保持最新，无需对任何人进行干预。

## 当Web服务器发生故障时 {#section-19280cf83ca44bd7b1ee11bfc74494d2}

当Web服务器因某种灾难性故障而完全脱机，或者不发送数据或心率时，停止时间的截止时间，以确保它代表从其感知到的所有数据源接收到的最后一次数据。 [!DNL data workbench server][!DNL data workbench server] 系统本身继续处理数据（仍可在Data Workbench中分析），但基于“开始时间”时间的任 [!DNL data workbench server] 何内容都不起作用。 例如，“开始时间”会触发报告，并用于在系统中创建许多派生维。 当“截止时间”停止时，不会触发报告，并且这些特定派生维不可用。

例如，如果WEB2在6月15日脱机，并且在5天内没有发送任何数据，则截止时间将在6月15日的某个时间。 例如，“昨天”的维度将是6月14日，即使今天的日期是6月20日。
