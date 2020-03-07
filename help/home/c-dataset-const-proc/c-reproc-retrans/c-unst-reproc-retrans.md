---
description: 在重新处理过程中，Data Workbench Server 会按照您在日志处理数据集配置文件和转换数据集配置文件中指定的内容重新构建数据集。
solution: Analytics
title: 了解重新处理和重新转换
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 了解重新处理和重新转换{#understanding-reprocessing-and-retransformation}

在重新处理过程中，Data Workbench Server 会按照您在日志处理数据集配置文件和转换数据集配置文件中指定的内容重新构建数据集。

为此，Data Workbench Server (InsightServer64.exe) 必须完成数据集构建的日志处理阶段和转换阶段。当日志处理完成时，系统会触发转换自动进行，但转换也可以独立进行，而不受日志处理的影响。

在日志处理阶段，Data Workbench 用户将无权访问数据集中的数据。而在转换阶段，Data Workbench 用户将有权访问最新的数据，但数据是采样的，并不完整。数据分析会在转换过程中继续执行，但只要发生转换，查询便将快速完成。

## 重新处理 {#section-92f1e46bf1534b3dba39e9493190b8ab}

每当您完成以下某个任务时，系统便会按照您在数据集配置文件中指定的内容自动进行日志处理，继而进行转换，以重新构建您的数据集。

* 添加新数据源。
* 在 [!DNL Profile.cfg] 文件中向群集添加新的 Data Workbench Server。
* Change the [!DNL Cluster.cfg] file.
* 更改文 [!DNL Log Processing.cfg] 件或文 [!DNL Log Processing Dataset Include] 件，包括但不限于：

   * 添加新参数
   * 更改转换
   * 更改 Start Time（开始时间）或 End Time（结束时间）参数

* Upgrade your [!DNL Insight Server.exe] file.

您还可以随时启动重新处理，方法是在 [!DNL Log Processing.cfg] 文件的 Reprocess（重新处理）参数中输入任意字符或字符组合并保存该文件。

>[!NOTE]
>
>For reprocessing to occur, the Pause parameter in the [!DNL Log Processing Mode.cfg] file must be set to false. 此参数的默认值为 false，因此可能不需要更改此参数。有关详细信息，请 [!DNL Log Processing Mode.cfg]参阅其 [他配置文件](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)。

## 重新转换 {#section-02446744549940ada8eba0573ec5575f}

Each time you change any information in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file, such as change a transformation or define a new dimension, transformation occurs automatically.

Each time you change lookup files that are referenced in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file (including lookup files for [!DNL Categorize], [!DNL FlatFileLookup], and [!DNL ODBCLookup] transformations), you must initiate transformation by entering any character or combination of characters in the Reprocess parameter of the [!DNL Transformation.cfg] file and saving the file.
