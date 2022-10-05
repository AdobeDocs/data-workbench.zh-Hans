---
description: Data Workbench 提供了一组转换，可允许 Data Workbench Server 将对照数据包含到数据集中。
title: 集成查找数据
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 90%

---

# 集成查找数据{#integrating-lookup-data}

{{eol}}

Data Workbench 提供了一组转换，可允许 Data Workbench Server 将对照数据包含到数据集中。

对照数据是来自公司数据库的外部数据，或者是可以与事件数据组合到一起来创建数据集的对照文件。通常，您使用对照数据扩充来自日志源的事件数据。从概念上讲，可以将使用对照数据视为用额外的信息列填充事件数据记录。

在使用对照数据时，您将数据加载到内存驻留对照表中。该表中的列必须包含一个事件数据记录中也存在的公共键。对照表本身中的数据可以从无格式文件或 ODBC 数据源加载。对照数据可以在数据集构建过程的日志处理阶段或转换阶段包含到数据集中。

若要包含对照数据，必须首先生成对照文件或者具有访问 SQL 数据库所需的信息，然后在用于日志处理和转换的数据集配置文件中定义以下一个或多个转换。

**将对照数据集成到数据集中**

1. 生成查找文件。 请参阅 [填充对照表](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. 在相应数据集配置文件的 Transformations（转换）参数中定义下列某种转换：

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>请注意， [!DNL ODBCLookup] 仅当在 [!DNL Transformation.cfg] 文件或 [!DNL Transformation Dataset Include] 文件。
