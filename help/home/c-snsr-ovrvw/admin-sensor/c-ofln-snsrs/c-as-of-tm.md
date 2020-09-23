---
description: 当数据工作台服务器从该源接收数据时，它会感知到数据源，如传感器。
solution: Analytics
title: 了解“开始”时间
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---


# 了解“开始”时间{#understanding-as-of-time}

当数据工作台服务器从该源接收数据时，它会感知到数据源，如传感器。

开始时间保证该数据 [!DNL data workbench server] 具有其所知的所有数据源的数据。

假设我们有三套将数据发 [!DNL Sensors] 送到以下站点 [!DNL data workbench server]:WEB1、WEB2和WEB3。 当接 [!DNL data workbench server] 收和处理来自这些源的 [!DNL Sensors]数据时，它会自动期望来自每个源的数据。 “开始时间”表示从所有这三个源 [!DNL data workbench server] 接收到的数据的上次时间。

实际上，他们 [!DNL data workbench server] 只关心“截止时间”，而不关心“截止时间”，或墙上某个时钟的时间。 时 [!DNL data workbench server] 间只知道时间。 这对于报告尤为重要，因为它保证报告始终基于截止时间运行，这可确保永远无法向系统的最终用户发送仅包含部分数据的报告。

使用 [!DNL data workbench server] 从发射器发送的数据来提供截止时间，无论是从网站收集的实际数据还是您发送的周期性心跳 [!DNL Sensors]。 这些心跳有两个目的：

1. 使和之间的HTTP/1.1永久连接 [!DNL Sensor] 保持打开 [!DNL data workbench server]。

1. 在未收集网站流量并将其发送到的事件中保持“截止时间”最新 [!DNL data workbench server]。

