---
description: 确保重新处理或重新转换顺利进行并及时完成，以便 Data Workbench 用户恢复工作的步骤。
title: 准备重新处理或重新转换
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 66%

---

# 准备重新处理或重新转换{#preparing-for-reprocessing-or-retransformation}

确保重新处理或重新转换顺利进行并及时完成，以便 Data Workbench 用户恢复工作的步骤。

1. 通过检查[!DNL Detailed Status]界面中数据集配置文件的[!DNL Processing Mode History]来确定上次处理或转换所经过的时间。

   1. 在处理数据集配置文件时，打开[!DNL Detailed Status]界面。
   1. 单击&#x200B;**[!UICONTROL Processing Status]** > ***[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]**&#x200B;以查看上次处理或转换所经过的时间。

      * “快速输入”是日志处理所需的总时间。
      * “快速合并”是转换所需的总时间。
      * 两个时间的总和（快速输入 + 快速合并）是处理数据集所需的总时间。

      以下示例显示日志处理耗时大约 43 秒，转换耗时不到 2 分钟。

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      有关[!DNL Detailed Status]界面的更多信息，请参阅&#x200B;*Data Workbench用户指南*。


1. 安排和规划重新处理。由于 Data Workbench 用户在日志处理阶段将无权访问数据，因此请确保您将重新处理安排在合适的时间（例如周末）进行。
1. 使用[!DNL Processing Legend.]中的字段监控重新处理和重新转换的进度。有关[!DNL Processing Legend]的详细信息，请参阅&#x200B;*Data Workbench用户指南*。
