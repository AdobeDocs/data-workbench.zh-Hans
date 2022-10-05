---
description: 指导分析可视化提供提示以便根据您在工作区中进行的选择进行进一步分析。
title: 指导分析
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 85%

---

# 指导分析{#guided-analysis}

{{eol}}

指导分析可视化提供提示以便根据您在工作区中进行的选择进行进一步分析。

该可视化帮助您标识哪些维度可以为您提供更多信息，即与您的选择相关性最强的维度。与以下 [!DNL Site] 指导分析可视化一样，您的 Adobe 应用程序中的指导分析可视化显示与您的数据集有关的维度。

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>如果维度名称以红色显示，则它未在数据集中定义。

当您在工作区中进行选择时，指导分析可视化在维度左侧显示复选标记，在右侧显示圆点，以显示哪个维度提供了最相关的信息：

* **复选标记**&#x200B;采用有统计意义的方式（也就是说，选择和基准之间的差别不是由于随机的原因）标识其值与基准不同的维度。
* **圆点**&#x200B;指示选择与基准不同的程度。第一个圆点表示U统计量，第二个圆点表示V统计量。 请参阅 [了解统计指标](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). 圆点越亮越大，差别越大，基于选择的维度的信息也就更相关（也就是说，圆点越亮越大表示信息更有用）。
