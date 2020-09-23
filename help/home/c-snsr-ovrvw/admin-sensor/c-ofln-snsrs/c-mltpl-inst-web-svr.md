---
description: 有关传感器在Web服务器上运行一个Web服务器实例时的常规配置的信息。
solution: Analytics
title: 使用 Web 服务器的多个实例
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---


# 使用 Web 服务器的多个实例{#working-with-multiple-instances-of-a-web-server}

有关传感器在Web服务器上运行一个Web服务器实例时的常规配置的信息。

![](assets/web_inst.png)

在这种情况下，单个Web服务器实例将数据写入内存映射队列文件，由发射器读取并发送到该队列 [!DNL data workbench server]。

当安 [!DNL Sensor] 装在运行多个收集器实例的Web服务器上时，您可以通过以下两种方式之一配置它：

* 可以让所有收集器模块共享一个队列文件。

   使用单个队列文件时，管理、配置和管理会有所简化，因为体系结构本身没那么复杂。 但是，对于单个队列文件，无论实例数量如何，整个Web服务器都标识为WEB1。

* 您可以多次复制上述架构，并使每个Web服务器实例都有一个单独的队列文件。

   这使您能够唯一地标识每个Web服务器实例。 换言之，Web服务器的标识(以及配置中的相应 [!DNL Sensor] 传感器ID)是此配置的函数。

无论如何，数据仍包含所有主机名信息，以便您能够区 [!DNL www.client.com]分 [!DNL www2.client.com]和等等。 正确的配置取决于分析目标以及分析师是否需要根据Web服务器上运行的特定实例对数据进行细分。

>[!NOTE]
>
>此类型的分段通常仅用于操作分析，在该区域之外不提供很多实际用途。

