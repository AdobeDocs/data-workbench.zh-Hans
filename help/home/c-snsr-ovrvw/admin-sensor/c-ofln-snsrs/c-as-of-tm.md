---
description: 当Data Workbench Server从该源接收数据时，它会感知到数据源（如传感器）。
solution: Insight
title: 了解“开始”时间
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解“开始”时间{#understanding-as-of-time}

当Data Workbench Server从该源接收数据时，它会感知到数据源（如传感器）。

截止时间可保证该数据 [!DNL data workbench server] 源具有其所感知到的所有数据源。

假设我们有三套将数据发 [!DNL Sensors] 送到以下站点 [!DNL data workbench server]:WEB1、WEB2和WEB3。 当从这 [!DNL data workbench server] 些源接收和处理数据时 [!DNL Sensors]，它会自动期望从这些源中的每个源获得数据。 “截止时间”表示从所有这三个源 [!DNL data workbench server] 接收到的数据的上次时间。

实际上， [!DNL data workbench server] 他们只关心“截止时间”，而不关心“墙时间”，或墙上某个时钟的时间。 时 [!DNL data workbench server] 间只知道“截止时间”。 这对于报告目的尤其重要，因为它保证报告始终基于截止时间运行，这确保只包含部分数据的报告永远无法发送给系统的最终用户。

使 [!DNL data workbench server] 用从发射机发送的数据来提供截止时间，无论是从网站收集的实际数据还是由您发送的周期性心跳 [!DNL Sensors]。 这些心跳有两个用途：

1. 使HTTP/1.1永久连接在和之 [!DNL Sensor] 间打开 [!DNL data workbench server]。

1. 在未收集网站流量并将其发送到时保持“截止时间”为最新 [!DNL data workbench server]。

