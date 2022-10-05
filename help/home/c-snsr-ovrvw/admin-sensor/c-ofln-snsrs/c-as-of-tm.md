---
description: 当Data Workbench Server从该源接收数据时，它会感知到数据源，如传感器。
title: 了解“开始”时间
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 了解“开始”时间{#understanding-as-of-time}

{{eol}}

当Data Workbench Server从该源接收数据时，它会感知到数据源，如传感器。

时间表保证 [!DNL data workbench server] 具有其感知到的所有数据源的数据。

假设我们有三组 [!DNL Sensors] 向 [!DNL data workbench server]:WEB1、WEB2和WEB3。 作为 [!DNL data workbench server] 接收和处理来自这些 [!DNL Sensors]，则会自动从每个源获取数据。 截止时间表示 [!DNL data workbench server] 从这三个来源接收了数据。

实际上， [!DNL data workbench server] 只关心“截止时间”，而不关心“截止时间”，或者“截止时间”。 的 [!DNL data workbench server] 只知道时间为“截止时间”。 这对于报告而言尤其重要，因为它可确保报表始终基于截止时间运行，这可确保仅包含部分数据的报表永远无法发送给系统的最终用户。

的 [!DNL data workbench server] 使用从发送器发送的数据来提供截止时间，无论是从网站收集的实际数据还是由您发送的周期性心率 [!DNL Sensors]. 这些心率有两个用途：

1. 要在 [!DNL Sensor] 和 [!DNL data workbench server].

1. 在未收集网站流量并将其发送到的情况下，使“截止时间”保持为最新 [!DNL data workbench server].
