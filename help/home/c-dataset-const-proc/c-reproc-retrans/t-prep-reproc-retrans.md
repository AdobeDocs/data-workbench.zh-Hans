---
description: 确保重新处理或重新转换顺利进行并及时完成，以便 Data Workbench 用户恢复工作的步骤。
solution: Analytics
title: 准备重新处理或重新转换
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 准备重新处理或重新转换{#preparing-for-reprocessing-or-retransformation}

确保重新处理或重新转换顺利进行并及时完成，以便 Data Workbench 用户恢复工作的步骤。

1. Determine the elapsed time of previous processing or transformation by checking the dataset profile&#39;s [!DNL Processing Mode History] in the [!DNL Detailed Status] interface.

   1. While working in your dataset profile, open the [!DNL Detailed Status] interface.
   1. 单击 **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>***[!UICONTROL Processing Mode History]** >以查看之前处理或转换的已用时间。

      * “快速输入”是日志处理所需的总时间。
      * “快速合并”是转换所需的总时间。
      * 两个时间的总和（快速输入 + 快速合并）是处理数据集所需的总时间。
      以下示例显示日志处理耗时大约 43 秒，转换耗时不到 2 分钟。

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      For more information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.


1. 安排和规划重新处理。由于 Data Workbench 用户在日志处理阶段将无权访问数据，因此请确保您将重新处理安排在合适的时间（例如周末）进行。
1. 使用“有关”的详细信息，请参阅《数据工作台用户指南》中 [!DNL Processing Legend.] 的字段，监视重新处理和重 [!DNL Processing Legend]新转换 *的进度*。
