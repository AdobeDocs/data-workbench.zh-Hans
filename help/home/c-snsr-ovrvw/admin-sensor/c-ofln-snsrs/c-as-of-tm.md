---
description: 当Data Workbench Server从该源接收数据时，它会感知到数据源，如传感器。
title: 了解“开始”时间
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 了解“开始”时间{#understanding-as-of-time}

当Data Workbench Server从该源接收数据时，它会感知到数据源，如传感器。

开始时间保证[!DNL data workbench server]具有它所感知到的所有数据源的数据。

假设我们有一组三个[!DNL Sensors]，它们将数据发送到[!DNL data workbench server]:WEB1、WEB2和WEB3。 当[!DNL data workbench server]接收并处理这些[!DNL Sensors]中的数据时，它会自动期望来自这些源中每个源的数据。 “截止时间”表示[!DNL data workbench server]从所有这三个源接收数据的上次时间。

实际上，[!DNL data workbench server]只关心“截止时间”，而不关心“截止时间”，或墙上某个时钟的时间。 [!DNL data workbench server]只将时间作为开始时间。 这对于报告来说尤为重要，因为它保证报表始终基于截止时间运行，这可确保永远不能向系统最终用户发送仅包含部分数据的报表。

[!DNL data workbench server]使用从发射器发送的数据来提供截止时间，无论是从网站收集的实际数据还是由[!DNL Sensors]发送的周期性心率。 这些心跳有两个目的：

1. 使[!DNL Sensor]和[!DNL data workbench server]之间的HTTP/1.1永久连接保持打开。

1. 使未收集网站流量并发送至[!DNL data workbench server]的事件中的“截止时间”保持最新。
