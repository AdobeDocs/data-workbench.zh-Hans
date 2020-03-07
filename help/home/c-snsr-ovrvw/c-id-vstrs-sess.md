---
description: 当从Web服务器收集事件数据时，传感器会自动为每个包含一个小随机标识符的访客设置一个永久cookie，而不会捕获任何个人身份信息。
solution: Insight
title: 传感器如何识别访客和会话？
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 传感器如何识别访客和会话？{#how-does-sensor-identify-visitors-and-sessions}

当从Web服务器收集事件数据时，传感器会自动为每个包含一个小随机标识符的访客设置一个永久cookie，而不会捕获任何个人身份信息。

此Adobe Cookie用于标识唯一访客及其所有相关会话。

默认情况下， [!DNL Sensor][!DNL Sensor] 从每个HTTP头捕获所有W3C扩展日志文件格式字段，但您可以配置为捕获客户端和服务器之间传输的任何头。 有关文件中收集的事件数据字段的 [!DNL Sensor] 信 [!DNL .vsl] 息，请参阅事 [件数据记录字段](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。

某些访客的浏览器不会永久存储cookie，并且很少数访客的浏览器根本不接受cookie（甚至会话cookie）。 即使它们只占网站总流量的一小部分，如果此类访客每次查看页面时被错误地计为整个会话，则可能导致严重错误计数，某些日志文件分析软件也会这样做。 Adobe通过使您能够分析有无Cookie的访客来解决此问题。

有关“中断的会话”过滤器的详细信息，请参阅《 *Data Workbench传感器指南》*。
