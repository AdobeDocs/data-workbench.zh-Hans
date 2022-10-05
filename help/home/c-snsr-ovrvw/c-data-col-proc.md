---
description: 传感器通过消除传统上涉及数据收集的大量人力，从您的Internet渠道中自动获取数据。
title: 数据收集流程的工作原理
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# 数据收集流程的工作原理{#how-does-the-data-collection-process-work}

{{eol}}

传感器通过消除传统上涉及数据收集的大量人力，从您的Internet渠道中自动获取数据。

在很多情况下，使用 [!DNL Sensor] 可以极大地简化您的数据管理流程。

当今的大型Internet、Extranet和Intranet站点通常在一系列Web服务器上运行。 生成的日志和数据可能会非常大且繁琐。 例如，如果您的网站运行30台Web服务器，则通常您的一名员工（或外包服务提供商的员工）将提取并整合30台服务器中每台的日志文件，然后对其运行报告。 安装 [!DNL Sensor] 在您的每台web服务器上，都会自动完成整个过程，从而减少您的开支，并使数据实时可用。

要自动执行此过程， [!DNL Sensor] 直接从每个web服务器收集网站上流量的原始信息。 原始数据 [!DNL Sensor] 捕获称为事件数据，与web服务器在其日志文件中记录的数据类型类似。

要捕获此数据，请在 [!DNL Sensor] 记录有关Web服务器处理的每个HTTP请求的信息。 [!DNL Sensor] 然后，缓冲信息以防止网络故障，并通过HTTP/S将信息安全地传输到 [!DNL data workbench server] 指定的。

在 [!DNL data workbench server] 接收数据，它会以高度压缩的方式处理和存储日志文件 [!DNL .vsl] 设置文件格式，使您能够轻松地在廉价硬件上维护大量数据。

有关收集的事件数据字段的信息，请参阅 [!DNL Sensor] in [!DNL .vsl] 文件，请参阅 [事件数据记录字段](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
