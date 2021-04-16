---
description: Dataset 目录中还包含其他一些文件，在操作软件或为您的 Adobe 实施提供其他功能时需要这些文件。
title: 其他文件
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 56%

---

# 其他文件{#other-files}

Dataset 目录中还包含其他一些文件，在操作软件或为您的 Adobe 实施提供其他功能时需要这些文件。

* **[!DNL Client.cfg:]** 用户档案 [!DNL Client.cfg] 的“数据集”目录中的文 [!DNL Base] 件是软件操作所必需的。请不要删除或修改 [!DNL Client.cfg] 文件中的任何参数。

* **[!DNL Cluster.cfg:]** 用户档案 [!DNL Cluster.cfg] 的“数据集”目录中的文 [!DNL Base] 件是软件操作所必需的。如果您要将数据集配置为在 Data Workbench Server 群集上处理，则在 [!DNL Cluster.cfg] 文件中，只应修改 Normalize Server（标准化服务器）参数。有关修改 Normalize Server（标准化服务器）参数的说明，请参阅[为群集创建集中标准化服务器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

* **[!DNL Insight Transform.cfg]和： [!DNL Insight Transform Mode.cfg]如** 果使用转换功能，则您在用户档案的“数据集”目录中有另外两 [!DNL Transform.cfg] 个配置 [!DNL TransformMode.cfg]文件：Data Workbench和 [!DNL Transform] Data Workbench。有关这些文件及其参数的信息，请参阅[转换功能](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)。

* **PAServer.cfg** 文件。如果您要将“预测分析”聚类作业提交至 Insight Server，则将需要配置 [!DNL PAServer.cfg] 文件以便处理服务器端聚类提交。自定义用户档案应从预测分析用户档案([!DNL Server\Profiles\Predictive Analytics\Dataset])继承[!DNL PAServer.cfg]。

   >[!IMPORTANT]
   >
   >在此文件中设置&#x200B;*主控服务器*&#x200B;并将[!DNL PAServer.cfg]保存到实现站点。
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
