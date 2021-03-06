---
description: 模型查看器让您可以使用倾向评分功能生成逻辑回归模型。
title: 模型查看器
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 100%

---

# 模型查看器{#model-viewer}

模型查看器让您可以使用倾向评分功能生成逻辑回归模型。

模型查看器显示每个输入变量（包括常数项）的系数加权及其统计误差范围。绝对系数高而误差幅度小的输入变量是模型中最重要的预测因素。

**打开模型查看器图表**

1. 选择 [!DNL Add Visualization > Predictive Analytics > Scoring]。
1. 将鼠标悬停在所保存得分的“模型完成”上。

![](assets/propensity_model_viewer.png)

系数大于等于 1 的输入变量对倾向模型有正面影响。小于 1 的系数对倾向模型有负面影响。括号中定义的范围是误差，表示成功人群中输入变量的一致性。
