---
description: 当Insight和Report的用户要处理和访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。
solution: Analytics
title: 关于 Insight Server 聚类
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 11%

---


# 关于 Insight Server 聚类{#about-insight-server-clusters}

当Insight和Report的用户要处理和访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。

通过设置群集， [!DNL Insight Server] 您可以在群集中的多台计算机上分发单个分析数据集，以利用多台计算机的处理能力 [!DNL Insight Servers]。

群集实施的第一步是 [!DNL Insight Server] 在群集中分 [!DNL Insight Server] 配计算机。 您设 [!DNL Insight Server] 置的第一台计算机是主控 [!DNL Insight Server] 计算机(有时称为主计 [!DNL Insight Server]算机)。

>[!NOTE]
>
>如果您使用的是 [!DNL Insight Server] 文件服务器单元(FSU),Adobe建议您将FSU配置为主控 [!DNL Insight Server]。 有关配置FSU的信息，请参阅《数据集配 *置指南》*。

主控管 [!DNL Insight Server] 理群集中的其他 [!DNL Insight Servers] 服务器(称为处理服务器，有时称为查询服务器)与和实例之间的 [!DNL Insight] 通信 [!DNL Report]。 对于给定数据集，对配置文件中指定的（一个或多个）指 [!DNL Insight Servers] 定(主控或处理)进行日志文 [!DNL Insight Server] 件处理。 在群集环境中工作时， [!DNL Insight] 将安装配置为访问主控, [!DNL Insight Server]但查询可以由群集中的任何一 [!DNL Insight Servers] 个成员处理。

>[!NOTE]
>
>**PAServer.cfg** 文件。如果您要将“预测分析”聚类作业提交至 Insight Server，则将需要配置 [!DNL PAServer.cfg] 文件以便处理服务器端聚类提交。The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site.
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>本章中的说明不适用于创建由五(5) [!DNL Insight Server] 个以上的群集 [!DNL Insight Servers]。 请联系Adobe，以获取系统要求以及针对超过五个群集的用户档案配置建议 [!DNL Insight Servers]。
