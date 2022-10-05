---
description: 当您要处理并让Insight和报表的用户能够访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。
title: 关于 Insight Server 聚类
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 11%

---

# 关于 Insight Server 聚类{#about-insight-server-clusters}

{{eol}}

当您要处理并让Insight和报表的用户能够访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。

通过设置 [!DNL Insight Server] 群集中，您可以在群集中的多台计算机之间分配单个分析数据集，以利用多台计算机的处理能力 [!DNL Insight Servers].

实施 [!DNL Insight Server] 群集将分配 [!DNL Insight Server] 群集中的计算机。 第一个 [!DNL Insight Server] 你设置的机器是你的主控 [!DNL Insight Server] (有时称为主 [!DNL Insight Server])。

>[!NOTE]
>
>如果您使用 [!DNL Insight Server] 文件服务器单元(FSU),Adobe建议您将FSU配置为主控 [!DNL Insight Server]. 有关配置FSU的信息，请参阅 *数据集配置指南*.

主控 [!DNL Insight Server] 管理另一个 [!DNL Insight Servers] 群集（称为处理服务器，有时称为查询服务器）和 [!DNL Insight] 和 [!DNL Report]. 对于给定的数据集，日志文件处理在（一个或多个）指定的 [!DNL Insight Servers] (主控或处理)，如 [!DNL Insight Server] 配置文件。 在群集环境中工作时， [!DNL Insight] 安装配置为访问主控 [!DNL Insight Server]，但查询可以由任何 [!DNL Insight Servers] 群集内。

>[!NOTE]
>
>**PAServer.cfg** 文件。如果您要将“预测分析”聚类作业提交至 Insight Server，则将需要配置 [!DNL PAServer.cfg] 文件以便处理服务器端聚类提交。自定义配置文件应继承 [!DNL PAServer.cfg] 从预测分析用户档案([!DNL Server\Profiles\Predictive Analytics\Dataset])。 设置 *主控服务器* 并保存 [!DNL PAServer.cfg] 到实施站点。
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
>本章中的说明不适用于创建 [!DNL Insight Server] 由五(5)个以上的组组成 [!DNL Insight Servers]. 请联系Adobe以获取超过5个群集的系统要求和配置文件配置建议 [!DNL Insight Servers].
