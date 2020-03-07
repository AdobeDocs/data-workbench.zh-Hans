---
description: 编辑 Transformation.cfg 文件时需要考虑的重要信息。
solution: Analytics
title: 有关转换配置文件的注意事项
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 有关转换配置文件的注意事项{#considerations-for-the-transformation-configuration-file}

编辑 Transformation.cfg 文件时需要考虑的重要信息。

* 更改此文件中的任何参数都需要重新转换数据。
* If you reprocess the data, you can check the [!DNL Transformation Progress] parameter in data workbench&#39;s [!DNL Processing Legend].

   有关重新处理数据的信息，请参阅重新 [!DNL Processing Legend,] 处理 [和重新转换](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL CrossRows]、 [!DNL ODBCLookup]、 [!DNL Sessionize]和 [!DNL AppendURI] 转换仅在文件中定义时才 [!DNL Transformation Dataset Configuration] 有效。 有关这些转换的信息，请参阅数 [据转换](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

   >[!NOTE]
   >
   >Adobe recommends defining transformations for the transformation phase of dataset construction in one or more [!DNL Transformation Dataset Include] files. 有关信息，请参 [阅转换数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。

* 您可以将上述任何参数添加到 [!DNL Transformation.cfg] 文件中，只需在记事本中打开并编辑该文件即可。当您在 Data Workbench 中重新打开该文件时，系统便会显示您做出并保存的所有更改。在添加新参数时，使用空格键（而不是 Tab 键）可向上一个标题级别的右侧缩进两 (2) 个空格。

   Any errors that occur during the transformation phase of the dataset construction process for a dataset profile are shown in the [!DNL Profiles] node of the [!DNL Detailed Status] interface in data workbench. For information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.

