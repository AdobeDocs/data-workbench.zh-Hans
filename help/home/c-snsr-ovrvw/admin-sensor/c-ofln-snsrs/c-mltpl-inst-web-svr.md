---
description: 有关传感器在Web服务器上运行一个Web服务器实例的常规配置的信息。
title: 使用 Web 服务器的多个实例
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# 使用 Web 服务器的多个实例{#working-with-multiple-instances-of-a-web-server}

有关传感器在Web服务器上运行一个Web服务器实例的常规配置的信息。

![](assets/web_inst.png)

在此方案中，单个Web服务器实例将数据写入内存映射队列文件，由发送器读取并发送到[!DNL data workbench server]。

当[!DNL Sensor]安装在运行多个收集器实例的Web服务器上时，可通过以下两种方式之一配置它：

* 您可以让所有收集器模块共享一个队列文件。

   使用单个队列文件时，管理、配置和管理会有所简化，因为体系结构本身不那么复杂。 但是，对于单个队列文件，无论实例数量如何，整个Web服务器都标识为WEB1。

* 您可以多次复制上述架构，并使每个Web服务器实例具有一个单独的队列文件。

   这使您能够唯一地标识每个Web服务器实例。 换句话说，Web服务器的标识（以及[!DNL Sensor]配置中的相应SensorID）是此配置的函数。

无论如何，数据仍包含所有主机名信息，以便您能够区分[!DNL www.client.com]、[!DNL www2.client.com]等。 正确的配置取决于分析目标，以及分析师是否需要根据Web服务器上运行的特定实例对数据进行细分。

>[!NOTE]
>
>此类分段通常仅在操作分析中使用，在该区域之外没有提供很多实际用途。
