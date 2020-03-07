---
description: 在编辑 Log Processing.cfg 文件时需考虑的概念性信息。
solution: Analytics
title: 有关日志处理配置文件的注意事项
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 有关日志处理配置文件的注意事项{#considerations-for-the-log-processing-configuration-file}

在编辑 Log Processing.cfg 文件时需考虑的概念性信息。

* 在定义数据集的源之后，不得在各目录之间移动数据文件。目录中只能添加由 Data Workbench Server 从传感器接收数据而生成的新建文件。
* 更改此文件中的任何参数都需要重新处理所有数据。必须将 [!DNL Log Processing Mode.cfg] 文件中的 Pause（暂停）参数设为 false 才能进行重新处理（请注意，此参数的默认值为 false，因此可能不需要更改此参数）。有关该文件的信 [!DNL Log Processing Mode.cfg] 息，请参 [阅其他配置文件](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)。

* If you reprocess the data, you can check the Log Processing Progress parameter in data workbench&#39;s [!DNL Processing Legend].

   有关重新处理数据的信息，请参阅重新 [处理和重新转换](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。 请参阅 [处理图例](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828)。

* [!DNL Log Processing.cfg] 文件可由多个数据集配置文件共享。[!DNL Log Processing.cfg] 文件中定义的转换会应用于共享此配置文件的所有数据集配置文件。

   >[!NOTE]
   >
   >Adobe recommends defining transformations for the log processing in one or more log processing [!DNL dataset include] files. 有关信息，请参阅 [日志处理数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)。

* 您可以将上述任何参数添加到 [!DNL Log Processing.cfg] 文件中，只需在记事本中打开并编辑该文件即可。当您在 Data Workbench 中重新打开该文件时，系统便会显示您做出并保存的所有更改。在添加新参数时，使用空格键（而不是 Tab 键）可向上一个标题级别的右侧缩进两 (2) 个空格。

   Any errors that occur during the log processing phase of the dataset construction process for a dataset profile are shown in the [!DNL Profiles] node of the [!DNL Detailed Status] interface in data workbench. For information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.

