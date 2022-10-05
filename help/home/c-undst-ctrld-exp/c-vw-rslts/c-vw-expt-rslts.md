---
description: 在将新字段添加到Log Processing.cfg并创建新的Split转换和扩展维度后，您可以在数据重新处理的快速输入阶段完成后立即查看您创建的新扩展维度。
solution: Analytics
title: 查看试验结果
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# 查看试验结果{#viewing-the-experiment-results}

{{eol}}

在将新字段添加到Log Processing.cfg并创建新的Split转换和扩展维度后，您可以在数据重新处理的快速输入阶段完成后立即查看您创建的新扩展维度。

默认情况下，此维度显示每个实验组的会话数。

**查看实验维度**

* 在 [!DNL Insight]，打开一个包含您创建的实验维度的表。

   实验维度元素，表示您当前运行的每个实验以及每个实验中的每个组，以每个组的当前会话数显示。 每个组的命名格式如下：使用实验名称后跟组名称：

   *实验名称。组名称*

   例如：[!DNL New Homepage.Control]

下表显示了在中创建的“对照实验组”维度 [!DNL Transformation.cfg] 每个实验和实验组。

新主页实验显示在表格底部，其中包含两组：控件和索引2.

![](assets/controlledexpgrps.png)

现在，您可以使用实验维度和任何相关量度来探索和解释实验结果，并创建详细描述这些结果的有用报告。
