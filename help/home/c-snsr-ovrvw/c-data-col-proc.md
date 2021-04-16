---
description: Sensor通过消除传统上涉及数据收集的大量人力，从您的Internet渠道中自动获取数据。
title: 数据收集流程的原理
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# 数据收集流程的原理{#how-does-the-data-collection-process-work}

Sensor通过消除传统上涉及数据收集的大量人力，从您的Internet渠道中自动获取数据。

在许多情况下，使用[!DNL Sensor]可以极大地简化数据管理过程。

当今的大型Internet、Extranet和Intranet站点通常在一组Web服务器上运行。 生成的日志和数据可能非常大，而且管理也很繁琐。 例如，如果您的站点运行30台Web服务器，通常您的某个员工(或外包服务提供商的员工)会在30台服务器上提取并合并每个日志文件，然后对其运行报告。 在每个Web服务器上安装[!DNL Sensor]将自动完成整个过程，从而减少开支并实时提供数据。

要自动完成此过程，[!DNL Sensor]会直接从每台Web服务器收集网站上流量的原始信息。 [!DNL Sensor]捕获的原始数据称为事件数据，与Web服务器在其日志文件中记录的数据类型相似。

要捕获此数据，[!DNL Sensor]中的检测记录有关Web服务器处理的每个HTTP请求的信息。 [!DNL Sensor] 然后缓冲信息以防止网络故障，并通过HTTP/S将信息安全地传输到您指 [!DNL data workbench server] 定的信息。

在[!DNL data workbench server]接收数据后，它将以高度压缩的[!DNL .vsl]格式文件处理和存储您的日志文件，从而使您能够轻松地在廉价硬件上维护大量数据。

有关[!DNL .vsl]文件中[!DNL Sensor]收集的事件数据字段的信息，请参阅[事件数据记录字段](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。
