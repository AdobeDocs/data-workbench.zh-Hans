---
description: Insight Server有两种许可证类型。
solution: Insight
title: 关于Insight Server许可证单元
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 关于Insight Server许可证单元{#about-insight-server-license-units}

Insight Server有两种许可证类型。

以下是两种许可类型：

* [数据处理单元(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [文件服务器单元 (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## 数据处理单元(DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

此类型 [!DNL Insight Server] 可以处理、存储和服务来自Adobe数据集的数据。 It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). DPU是与客户端直接 [!DNL Insight Server] 交互 [!DNL Insight] 的 [!DNL Report] 类型。

如果您正在安装 [!DNL Insight Server] DPU，请参 [阅Insight Server DPU的安装过程](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)。

## 文件服务器单元 (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

这种类型的服务器被配置为从一个或多个或事件数据复制实例（具有特殊使用许可证的功能）接收和存储事件数据，并将该数据流化到一个或多个数据处理单元( [!DNL Sensor][!DNL Repeater][!DNL Insight Server] DPU)，以构建Adobe数据集。 DPU使用协议与FSU通信，该协议优化了事件数据到DPU的传输，并且比在普通文件服务器上维护日志文件要快得多。 The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

如果您正在安装 [!DNL Insight Server] FSU，请参 [阅Insight Server FSU的安装过程](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。
