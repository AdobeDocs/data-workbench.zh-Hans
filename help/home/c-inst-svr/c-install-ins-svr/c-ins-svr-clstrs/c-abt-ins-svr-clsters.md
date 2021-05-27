---
description: 当您要处理并让Insight和报表的用户能够访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。
title: 关于 Insight Server 聚类
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 11%

---

# 关于 Insight Server 聚类{#about-insight-server-clusters}

当您要处理并让Insight和报表的用户能够访问的数据量超过单个Insight Server的容量时，需要Insight Server群集。

通过设置[!DNL Insight Server]群集，您可以在群集中的多台计算机之间分配单个分析数据集，以利用多个[!DNL Insight Servers]的处理能力。

[!DNL Insight Server]群集实现的第一步是在群集中分配[!DNL Insight Server]计算机。 您设置的第一台[!DNL Insight Server]计算机是主控的[!DNL Insight Server]（有时称为主[!DNL Insight Server]）。

>[!NOTE]
>
>如果您使用的是[!DNL Insight Server]文件服务器单元(FSU)，则Adobe建议将FSU配置为主控的[!DNL Insight Server]。 有关配置FSU的信息，请参阅&#x200B;*《数据集配置指南》*。

主控[!DNL Insight Server]管理群集中其他[!DNL Insight Servers]（称为处理服务器，有时称为查询服务器）与[!DNL Insight]和[!DNL Report]实例之间的通信。 对于给定数据集，日志文件处理在（一个或多个）指定的[!DNL Insight Servers](主控或处理)中（在[!DNL Insight Server]配置文件中指定）进行。 在群集环境中工作时， [!DNL Insight]安装配置为访问主控[!DNL Insight Server]，但可由群集中的任何[!DNL Insight Servers]处理查询。

>[!NOTE]
>
>**PAServer.cfg** 文件。如果您要将“预测分析”聚类作业提交至 Insight Server，则将需要配置 [!DNL PAServer.cfg] 文件以便处理服务器端聚类提交。自定义配置文件应从预测分析配置文件([!DNL Server\Profiles\Predictive Analytics\Dataset])继承[!DNL PAServer.cfg]。 在此文件中设置一个&#x200B;*主控服务器*，然后将[!DNL PAServer.cfg]保存到实施站点。
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
>本章中的说明不适用于创建包含五(5)个以上[!DNL Insight Servers]的[!DNL Insight Server]群集。 请联系Adobe，以获取超过5个[!DNL Insight Servers]的群集的系统要求和配置文件配置建议。
