---
description: Insight Server有两种许可证类型。
title: 关于 Insight Server 许可单元
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# 关于 Insight Server 许可单元{#about-insight-server-license-units}

Insight Server有两种许可证类型。

以下是两种许可证类型：

* [数据处理单元(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [文件服务器单元 (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## 数据处理单元(DPU){#section-bf589e13cf5c43a58f8f85a457de6f65}

此类型的[!DNL Insight Server]可以处理、存储和提供来自Adobe数据集的数据。 它可以选择存储包含构建数据集的源数据的日志文件，也可以从[!DNL Insight Server]文件服务器单元(FSU)接收该数据。 DPU是[!DNL Insight Server]类型，[!DNL Insight]和[!DNL Report]客户端直接与之交互。

如果您正在安装[!DNL Insight Server] DPU，请参阅[Insight Server DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)的安装过程。

## 文件服务器单元 (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

此类型的服务器被配置为接收和存储来自一个或多个[!DNL Sensor]或事件数据复制实例（[!DNL Repeater]功能，随特殊使用许可证提供）的事件数据，并将该数据流传输到一个或多个[!DNL Insight Server]数据处理单元(DPU)，以构建Adobe数据集。 DPU使用协议与FSU通信，该协议优化了事件数据到DPU的传输，并且比在普通文件服务器上维护日志文件的速度要快得多。 使用FSU还通过使日志数据能够存储在成本较低的存储硬件上而降低了硬件成本，并通过允许多个[!DNL Sensors]指向单个[!DNL Insight Server]而降低了管理复杂性。

如果要安装[!DNL Insight Server] FSU，请参阅[Insight Server FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)的安装过程。
