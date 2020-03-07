---
description: 指导分析可视化提供提示以便根据您在工作区中进行的选择进行进一步分析。
solution: Analytics
title: 向导式分析
topic: Data workbench
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Guided analysis{#guided-analysis}

指导分析可视化提供提示以便根据您在工作区中进行的选择进行进一步分析。

该可视化帮助您标识哪些维度可以为您提供更多信息，即与您的选择相关性最强的维度。与以下 [!DNL Site] 指导分析可视化一样，您的 Adobe 应用程序中的指导分析可视化显示与您的数据集有关的维度。

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>如果维名称以红色显示，则该名称在数据集中未定义。

当您在工作区中进行选择时，指导分析可视化在维度左侧显示复选标记，在右侧显示圆点，以显示哪个维度提供了最相关的信息：

* **复选标记**&#x200B;采用有统计意义的方式（也就是说，选择和基准之间的差别不是由于随机的原因）标识其值与基准不同的维度。
* **圆点**&#x200B;指示选择与基准不同的程度。第一点表示U统计，第二点表示V统计。 See [Understanding the Statistical Measures](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). 圆点越亮越大，差别越大，基于选择的维度的信息也就更相关（也就是说，圆点越亮越大表示信息更有用）。

