---
description: 在从Web服务器收集事件数据时，传感器会自动为每个包含小型随机标识符的访客设置永久性Cookie，而不会捕获任何个人身份信息。
title: 传感器如何识别访客和会话？
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# 传感器如何识别访客和会话？{#how-does-sensor-identify-visitors-and-sessions}

在从Web服务器收集事件数据时，传感器会自动为每个包含小型随机标识符的访客设置永久性Cookie，而不会捕获任何个人身份信息。

此AdobeCookie用于识别独特访客及其所有相关会话。

默认情况下，[!DNL Sensor]会从每个HTTP标头中捕获所有W3C扩展日志文件格式字段，但您可以配置[!DNL Sensor]以捕获客户端和服务器之间传输的任何标头。 有关[!DNL Sensor]在[!DNL .vsl]文件中收集的事件数据字段的信息，请参阅[事件数据记录字段](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。

某些访客的浏览器不会永久存储Cookie，并且极少数的访客的浏览器根本不接受Cookie（甚至是会话Cookie）。 即使它们只占网站总流量的一小部分，但如果此类访客的每次页面查看被错误地计为整个会话，则它们可能会导致重大错误计数，就像某些日志文件分析软件所做的那样。 Adobe可解决此问题，方法是允许您分析具有或不使用Cookie的访客。

有关“中断的会话”筛选器的详细信息，请参阅&#x200B;*Data Workbench传感器指南*。
