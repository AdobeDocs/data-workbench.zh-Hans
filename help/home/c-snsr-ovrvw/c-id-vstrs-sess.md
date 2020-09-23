---
description: 当从Web服务器收集事件数据时，传感器会自动为每个包含小随机标识符的访客设置永久cookie，而不会捕获任何个人身份信息。
solution: Analytics
title: 传感器如何识别访客和会话？
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---


# 传感器如何识别访客和会话？{#how-does-sensor-identify-visitors-and-sessions}

当从Web服务器收集事件数据时，传感器会自动为每个包含小随机标识符的访客设置永久cookie，而不会捕获任何个人身份信息。

此Adobecookie用于标识唯一访客及其所有相关会话。

默认情 [!DNL Sensor] 况下，从每个HTTP头捕获所有W3C扩展日志文件格式字段，但您可以配置 [!DNL Sensor] 捕获客户端和服务器之间传输的任何头。 有关文件中收集的事件数据字段 [!DNL Sensor] 的 [!DNL .vsl] 信息，请参 [阅事件数据记录字段](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。

某些访客的浏览器不会永久存储cookie，并且非常少数访客的浏览器根本不接受cookie（甚至会话cookie）。 即使这些视图只占网站总流量的一小部分，如果此类访客的每页分析被错误地计为整个会话，则可能会导致严重的错误计数。 Adobe通过使您能够分析包含和不使用cookies的访客来解决此问题。

有关“中断的会话过滤器”的详细信息，请参阅《 *Data Workbench传感器指南》*。
