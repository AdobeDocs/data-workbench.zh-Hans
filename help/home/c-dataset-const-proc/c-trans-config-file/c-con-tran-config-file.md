---
description: 编辑 Transformation.cfg 文件时需要考虑的重要信息。
title: 有关转换配置文件的注意事项
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 49%

---

# 有关转换配置文件的注意事项{#considerations-for-the-transformation-configuration-file}

编辑 Transformation.cfg 文件时需要考虑的重要信息。

* 更改此文件中的任何参数都需要重新转换数据。
* 如果重新处理数据，则可以检查Data Workbench的[!DNL Processing Legend]中的[!DNL Transformation Progress]参数。

   有关重新处理数据或[!DNL Processing Legend,]的信息，请参阅[重新处理和重新转换](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL CrossRows]、、 [!DNL ODBCLookup]、 [!DNL Sessionize]和转 [!DNL AppendURI] 换仅在文件中定义时才 [!DNL Transformation Dataset Configuration] 有效。有关这些转换的信息，请参阅[数据转换](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

   >[!NOTE]
   >
   >Adobe建议在一个或多个[!DNL Transformation Dataset Include]文件中为数据集构建的转换阶段定义转换。 有关信息，请参阅[转换数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。

* 您可以将上述任何参数添加到 [!DNL Transformation.cfg] 文件中，只需在记事本中打开并编辑该文件即可。当您在 Data Workbench 中重新打开该文件时，系统便会显示您做出并保存的所有更改。在添加新参数时，使用空格键（而不是 Tab 键）可向上一个标题级别的右侧缩进两 (2) 个空格。

   数据集用户档案的数据集构建过程的转换阶段发生的任何错误都显示在Data Workbench中[!DNL Detailed Status]接口的[!DNL Profiles]节点中。 有关[!DNL Detailed Status]接口的信息，请参阅&#x200B;*《Data Workbench用户指南》*。
