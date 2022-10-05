---
description: 编辑 Transformation.cfg 文件时需要考虑的重要信息。
title: 有关转换配置文件的注意事项
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 49%

---

# 有关转换配置文件的注意事项{#considerations-for-the-transformation-configuration-file}

{{eol}}

编辑 Transformation.cfg 文件时需要考虑的重要信息。

* 更改此文件中的任何参数都需要重新转换数据。
* 如果重新处理数据，则可以检查 [!DNL Transformation Progress] data workbench中的参数 [!DNL Processing Legend].

   有关重新处理数据或 [!DNL Processing Legend,] 请参阅 [重新处理和重新转换](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]和 [!DNL AppendURI] 转换仅在 [!DNL Transformation Dataset Configuration] 文件。 有关这些转换的信息，请参阅 [数据转换](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe建议为一个或多个数据集构建的转换阶段定义转换 [!DNL Transformation Dataset Include] 文件。 有关信息，请参阅 [转换数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* 您可以将上述任何参数添加到 [!DNL Transformation.cfg] 文件中，只需在记事本中打开并编辑该文件即可。当您在 Data Workbench 中重新打开该文件时，系统便会显示您做出并保存的所有更改。在添加新参数时，使用空格键（而不是 Tab 键）可向上一个标题级别的右侧缩进两 (2) 个空格。

   在数据集构建过程的转换阶段期间发生的数据集配置文件的任何错误都会显示在 [!DNL Profiles] 节点 [!DNL Detailed Status] data workbench中的界面。 有关 [!DNL Detailed Status] 界面，请参阅 *Data Workbench用户指南*.
