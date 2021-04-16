---
description: 在重新处理过程中，Data Workbench Server 会按照您在日志处理数据集配置文件和转换数据集配置文件中指定的内容重新构建数据集。
title: 了解重新处理和重新转换
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 69%

---

# 了解重新处理和重新转换{#understanding-reprocessing-and-retransformation}

在重新处理过程中，Data Workbench Server 会按照您在日志处理数据集配置文件和转换数据集配置文件中指定的内容重新构建数据集。

为此，Data Workbench Server (InsightServer64.exe) 必须完成数据集构建的日志处理阶段和转换阶段。当日志处理完成时，系统会触发转换自动进行，但转换也可以独立进行，而不受日志处理的影响。

在日志处理阶段，Data Workbench 用户将无权访问数据集中的数据。而在转换阶段，Data Workbench 用户将有权访问最新的数据，但数据是采样的，并不完整。数据分析会在转换过程中继续执行，但只要发生转换，查询便将快速完成。

## 重新处理 {#section-92f1e46bf1534b3dba39e9493190b8ab}

每当您完成以下某个任务时，系统便会按照您在数据集配置文件中指定的内容自动进行日志处理，继而进行转换，以重新构建您的数据集。

* 添加新数据源。
* 在 [!DNL Profile.cfg] 文件中向群集添加新的 Data Workbench Server。
* 更改[!DNL Cluster.cfg]文件。
* 更改[!DNL Log Processing.cfg]文件或[!DNL Log Processing Dataset Include]文件，包括但不限于：

   * 添加新参数
   * 更改转换
   * 更改 Start Time（开始时间）或 End Time（结束时间）参数

* 升级您的[!DNL Insight Server.exe]文件。

您还可以随时启动重新处理，方法是在 [!DNL Log Processing.cfg] 文件的 Reprocess（重新处理）参数中输入任意字符或字符组合并保存该文件。

>[!NOTE]
>
>要进行重新处理，必须将[!DNL Log Processing Mode.cfg]文件中的Pause参数设置为false。 此参数的默认值为 false，因此可能不需要更改此参数。有关[!DNL Log Processing Mode.cfg]的详细信息，请参阅[其他配置文件](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)。

## 重新转换 {#section-02446744549940ada8eba0573ec5575f}

每次您更改[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件中的任何信息（如更改转换或定义新维度）时，都会自动进行转换。

每次更改在[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件（包括[!DNL Categorize]、[!DNL FlatFileLookup]和[!DNL ODBCLookup]转换的查找文件）中引用的查找文件时，必须在[!DNL Transformation.cfg]文件的“重新处理”参数中输入任何字符或字符组合并保存文件，以启动转换。
