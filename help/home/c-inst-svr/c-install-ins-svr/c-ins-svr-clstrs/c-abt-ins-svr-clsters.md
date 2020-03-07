---
description: 当Insight和Report的用户要处理和访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。
solution: Insight
title: 关于Insight Server群集
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 关于Insight Server群集{#about-insight-server-clusters}

当Insight和Report的用户要处理和访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。

通过设置群集， [!DNL Insight Server] 您可以在群集中的多台计算机上分发单个分析数据集，以利用多台计算机的处理能力 [!DNL Insight Servers]。

群集实现的第一步是 [!DNL Insight Server] 在群集中分配 [!DNL Insight Server] 计算机。 您设置 [!DNL Insight Server] 的第一台计算机是主计算机 [!DNL Insight Server] (有时称为主计算机 [!DNL Insight Server])。

>[!NOTE]
>
>如果您使用的 [!DNL Insight Server] 是文件服务器单元(FSU),Adobe建议您将FSU配置为主服务器 [!DNL Insight Server]。 有关配置FSU的信息，请参阅《数据集配 *置指南》*。

主设备 [!DNL Insight Server] 管理群集中的其他 [!DNL Insight Servers] 服务器（称为处理服务器，或有时称为查询服务器）与和实例之间的 [!DNL Insight] 通信 [!DNL Report]。 对于给定数据集，日志文件处理会按配置文件中指定的（一个或多个）指 [!DNL Insight Servers] 定（主数据集或处理数据集）进 [!DNL Insight Server] 行。 在群集环境中工作时， [!DNL Insight] 将安装配置为访问主设备， [!DNL Insight Server]但查询可以由群集中的任何一个 [!DNL Insight Servers] 设备处理。

>[!NOTE]
>
>**PAServer.cfg** 文件。如果您要将“预测分析”聚类作业提交至 Insight Server，则将需要配置 [!DNL PAServer.cfg] 文件以便处理服务器端聚类提交。The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ( [!DNL Server\Profiles\Predictive Analytics\Dataset]). Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site. >
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>本章中的说明不适用于创建由五(5) [!DNL Insight Server] 个以上的群集 [!DNL Insight Servers]。 请联系Adobe，获取超过5个群集的系统要求和配置文件配置建议 [!DNL Insight Servers]。

