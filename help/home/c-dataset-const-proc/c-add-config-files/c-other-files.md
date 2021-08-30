---
description: Dataset 目录中还包含其他一些文件，在操作软件或为您的 Adobe 实施提供其他功能时需要这些文件。
title: 其他文件
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 57%

---

# 其他文件{#other-files}

Dataset 目录中还包含其他一些文件，在操作软件或为您的 Adobe 实施提供其他功能时需要这些文件。

* **[!DNL Client.cfg:]** 软件 [!DNL Client.cfg] 操作时，需要配置文件 [!DNL Base] 的Dataset目录内的文件。请不要删除或修改 [!DNL Client.cfg] 文件中的任何参数。

* **[!DNL Cluster.cfg:]** 软件 [!DNL Cluster.cfg] 操作时，需要配置文件 [!DNL Base] 的Dataset目录内的文件。如果您要将数据集配置为在 Data Workbench Server 群集上处理，则在 [!DNL Cluster.cfg] 文件中，只应修改 Normalize Server（标准化服务器）参数。有关修改 Normalize Server（标准化服务器）参数的说明，请参阅[为群集创建集中标准化服务器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

* **[!DNL Insight Transform.cfg]和： [!DNL Insight Transform Mode.cfg]** 如果您使用转换功能，则配置文件的Dataset目录中还有两个其 [!DNL Transform.cfg] 他配置文 [!DNL TransformMode.cfg]件，即Data Workbench和 [!DNL Transform] Data Workbench 。有关这些文件及其参数的信息，请参阅[转换功能](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html)。

* **PAServer.cfg** 文件。如果您要将“预测分析”聚类作业提交至 Insight Server，则将需要配置 [!DNL PAServer.cfg] 文件以便处理服务器端聚类提交。自定义配置文件应从预测分析配置文件([!DNL Server\Profiles\Predictive Analytics\Dataset])继承[!DNL PAServer.cfg]。

   >[!IMPORTANT]
   >
   >在此文件中设置一个&#x200B;*主控服务器*，然后将[!DNL PAServer.cfg]保存到实施站点。
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
