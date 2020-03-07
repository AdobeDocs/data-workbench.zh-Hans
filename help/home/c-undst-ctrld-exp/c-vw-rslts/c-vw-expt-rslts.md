---
description: 在将新字段添加到Log Processing.cfg并创建新的Split转换和扩展维之后，您可以在数据重新处理的快速输入阶段完成后立即查看您创建的新扩展维。
solution: Insight,Analytics
title: 查看实验结果
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查看实验结果{#viewing-the-experiment-results}

在将新字段添加到Log Processing.cfg并创建新的Split转换和扩展维之后，您可以在数据重新处理的快速输入阶段完成后立即查看您创建的新扩展维。

默认情况下，该维度显示每个实验组的会话数。

**查看实验尺寸**

* 在中的任何工 [!DNL Insight]作区中，打开一个包含您创建的实验维度的表。

   实验维度元素（表示您当前运行的每个实验以及每个实验中的每个组）显示每个组的当前会话数。 每个组使用实验名称后跟组名称，以下格式命名：

   *实验名称。组名称*

   例如：[!DNL New Homepage.Control]

下表显示了在各个实验及其组中创建 [!DNL Transformation.cfg] 的“受控实验组”尺寸。

新主页实验显示在表的底部，其两组：控件和索引2。

![](assets/controlledexpgrps.png)

您现在可以使用实验维度和任何相关指标来探索和解释实验结果，并创建详细描述这些结果的有用报告。
