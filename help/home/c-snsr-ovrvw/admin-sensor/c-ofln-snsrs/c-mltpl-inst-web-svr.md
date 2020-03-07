---
description: 有关传感器的常规配置的信息，该传感器在Web服务器上运行一个Web服务器实例。
solution: Insight
title: 使用Web服务器的多个实例
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用Web服务器的多个实例{#working-with-multiple-instances-of-a-web-server}

有关传感器的常规配置的信息，该传感器在Web服务器上运行一个Web服务器实例。

![](assets/web_inst.png)

在这种情况下，单个Web服务器实例将数据写入存储器映射队列文件，由发射机读取并发送到该队列文件 [!DNL data workbench server]。

当安 [!DNL Sensor] 装在运行多个收集器实例的Web服务器上时，可以通过以下两种方式之一配置它：

* 您可以让所有收集器模块共享一个队列文件。

   使用单个队列文件时，管理、配置和管理会有所简化，因为体系结构本身没那么复杂。 但是，对于单个队列文件，无论实例的数量如何，整个Web服务器都标识为WEB1。

* 您可以多次复制上述架构，并使每个Web服务器实例都有一个单独的队列文件。

   这使您能够唯一地标识每个Web服务器实例。 换句话说，Web服务器（以及配置中相应的SensorID）的标识 [!DNL Sensor] 是此配置的功能。

无论如何，数据仍包含所有主机名信息，以便您能够区 [!DNL www.client.com]分 [!DNL www2.client.com]和等等。 正确的配置取决于分析目标以及分析人员是否需要根据在Web服务器上运行的特定实例对数据进行细分。

>[!NOTE]
>
>此类细分通常仅用于操作分析，在该领域之外不提供很多实际用途。

