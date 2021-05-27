---
description: 当Data Workbench Server从该源接收数据时，它会感知到数据源，如传感器。
title: 了解“开始”时间
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 了解“开始”时间{#understanding-as-of-time}

当Data Workbench Server从该源接收数据时，它会感知到数据源，如传感器。

截止时间可保证[!DNL data workbench server]具有其感知到的所有数据源的数据。

假设我们有一组由三个[!DNL Sensors]组成的集合，用于将数据发送到[!DNL data workbench server]:WEB1、WEB2和WEB3。 当[!DNL data workbench server]从这些[!DNL Sensors]接收和处理数据时，它会自动从这些源中获得数据。 截止时间表示[!DNL data workbench server]上次从所有这三个源接收数据的时间。

实际上，[!DNL data workbench server]只关心“截止时间”，而不关心“截止时间”，或墙上时钟的时间。 [!DNL data workbench server]只知道该时间为“截止时间”。 这对于报告而言尤其重要，因为它可确保报表始终基于截止时间运行，这可确保仅包含部分数据的报表永远无法发送给系统的最终用户。

[!DNL data workbench server]使用从发送器发送的数据来提供截止时间，无论是从网站收集的实际数据还是由[!DNL Sensors]发送的周期性心率。 这些心率有两个用途：

1. 保持在[!DNL Sensor]和[!DNL data workbench server]之间打开HTTP/1.1永久连接。

1. 在未收集网站流量并将其发送到[!DNL data workbench server]的情况下，保持“截止时间”为最新值。
