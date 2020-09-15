---
description: Dataset 目录中还包含其他一些文件，在操作软件或为您的 Adobe 实施提供其他功能时需要这些文件。
solution: Analytics
title: 其他文件
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 56%

---


# 其他文件{#other-files}

Dataset 目录中还包含其他一些文件，在操作软件或为您的 Adobe 实施提供其他功能时需要这些文件。

* **[!DNL Client.cfg:]** 用户档案 [!DNL Client.cfg] 的“数据集”目录中的文 [!DNL Base] 件是软件操作所必需的。 请不要删除或修改 [!DNL Client.cfg] 文件中的任何参数。

* **[!DNL Cluster.cfg:]** 用户档案 [!DNL Cluster.cfg] 的“数据集”目录中的文 [!DNL Base] 件是软件操作所必需的。 如果您要将数据集配置为在 Data Workbench Server 群集上处理，则在 [!DNL Cluster.cfg] 文件中，只应修改 Normalize Server（标准化服务器）参数。有关修改 Normalize Server（标准化服务器）参数的说明，请参阅[为群集创建集中标准化服务器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

* **[!DNL Insight Transform.cfg]和[!DNL Insight Transform Mode.cfg]:** 如果您使用的是转换功能，则在用户档案的“数据集”目录 [!DNL Transform.cfg] 中还有 [!DNL TransformMode.cfg]两个额外的配置文件：数据工作台和数据工 [!DNL Transform] 作台。 For information about these files and their parameters, see [Transform Functionality](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* **PAServer.cfg** 文件。如果您要将“预测分析”聚类作业提交至 Insight Server，则将需要配置 [!DNL PAServer.cfg] 文件以便处理服务器端聚类提交。The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```

