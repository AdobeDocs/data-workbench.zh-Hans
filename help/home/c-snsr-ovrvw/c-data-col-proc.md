---
description: 传感器通过消除传统上涉及数据收集的大量人力，从您的Internet渠道自动获取数据。
solution: Analytics
title: 数据收集流程的原理
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---


# 数据收集流程的原理{#how-does-the-data-collection-process-work}

传感器通过消除传统上涉及数据收集的大量人力，从您的Internet渠道自动获取数据。

在许多情况下，使 [!DNL Sensor] 用可以极大地简化数据管理过程。

当今的大型Internet、Extranet和Intranet站点通常在一组Web服务器上运行。 生成的日志和数据可能非常大，而且管理起来很麻烦。 例如，如果您的站点运行30台Web服务器，通常您的某个员工(或外包服务提供商的员工)会将每个日志文件从30台服务器中抽取并合并，然后对它们运行报告。 在每 [!DNL Sensor] 台Web服务器上进行安装可自动完成整个过程，从而减少开支并实时提供数据。

要自动完成此过程 [!DNL Sensor] ，请直接从每台Web服务器收集网站上流量的原始信息。 捕获的原始 [!DNL Sensor] 数据称为事件数据，与Web服务器在其日志文件中记录的数据类型相似。

要捕获此数据，在中的检 [!DNL Sensor] 测记录Web服务器处理的每个HTTP请求的相关信息。 [!DNL Sensor] 然后缓冲信息以防止网络故障，并通过HTTP/S将信息安全地传输到您指 [!DNL data workbench server] 定的信息。

收到数 [!DNL data workbench server] 据后，它会以高度压缩的格式文件处理和存储您 [!DNL .vsl] 的日志文件，从而使您能够在便宜的硬件上轻松维护大量数据。

有关文件中收集的事件数据字段 [!DNL Sensor] 的 [!DNL .vsl] 信息，请参 [阅事件数据记录字段](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。
