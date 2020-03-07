---
description: Sensor通过消除传统上参与数据收集的大量人力，从Internet渠道自动获取数据。
solution: Insight
title: 数据收集过程是如何工作的？
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 数据收集过程是如何工作的？{#how-does-the-data-collection-process-work}

Sensor通过消除传统上参与数据收集的大量人力，从Internet渠道自动获取数据。

在许多情况下，使 [!DNL Sensor] 用可以极大地简化数据管理过程。

当今的大型Internet、Extranet和Intranet站点通常在一系列Web服务器上运行。 生成的日志和数据可能非常大，并且管理起来很麻烦。 例如，如果您的站点运行30台Web服务器，通常您的某个员工（或外包服务提供商的员工）会在30台服务器中的每一台上提取并合并每个日志文件，然后对其运行报告。 在每 [!DNL Sensor] 台Web服务器上安装可自动完成整个过程，从而减少开支并实时提供数据。

要自动完成此过程， [!DNL Sensor] 请直接从每台Web服务器收集网站上流量的原始信息。 捕获的原始数 [!DNL Sensor] 据称为事件数据，与Web服务器在其日志文件中记录的数据类型类似。

要捕获此数据，Web服务器处 [!DNL Sensor] 理的每个HTTP请求的相关信息均记录在内。 [!DNL Sensor] 然后，缓冲信息以防止网络故障，并通过HTTP/S安全地将信息传输到您指 [!DNL data workbench server] 定的位置。

接收数 [!DNL data workbench server] 据后，它会以高度压缩的格式文件处理和存储您的日志文件，从而使您能够在价格低廉的硬件上轻松 [!DNL .vsl] 地维护大量数据。

有关文件中收集的事件数据字段的 [!DNL Sensor] 信 [!DNL .vsl] 息，请参阅事 [件数据记录字段](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。
