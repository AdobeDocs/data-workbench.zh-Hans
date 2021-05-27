---
description: 在运行该实验直到参与该实验的访客达到所需的最小数量为止后，您可以确保有足够的统计置信度来评估实验结果。
solution: Analytics,Analytics
title: 评估实验
uuid: 88fd81bc-b944-48ea-bd4d-8716979ec69e
exl-id: 5add2168-f6bc-45c5-bf1d-1191a38c5bac
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# 评估实验{#evaluating-the-experiment}

在运行该实验直到参与该实验的访客达到所需的最小数量为止后，您可以确保有足够的统计置信度来评估实验结果。

使用[!DNL Insight]，比较作为假设的一部分定义的任何量度或关键绩效指标，以确定实验是否成功（即，假设已通过指定置信度验证）。

在我们的示例实验中，如果访客转化率至少提高了1.5%（这是我们之前定义的成功标准），则证明了我们的假设是正确的。

以下工作区示例显示，index2测试组的“转化”实际上比控制组高1.8%，证明了我们的假设。

![](assets/experimentresults.png)

* [总结实验结果](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-24a496c080a04e929764094acb00bab7)
* [根据结果采取行动](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1623e26ced524fd9beab48ac1f9165d9)
* [监控您的操作](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1954311950c34637800cbd7c0711983f)

## 实验结果{#section-24a496c080a04e929764094acb00bab7}综述

使用[!DNL Insight]，可以创建详细报告以汇总和说明实验结果。

然后，您可以使用报表（如以下示例所示）根据结果提出推荐，这些结果由您在报表中提供的可视化信息作为备份：

![](assets/experimentresults2.png)

## 根据结果{#section-1623e26ced524fd9beab48ac1f9165d9}执行操作

结果清楚后，您就可以根据这些结果采取行动，方法是：对测试页面进行生产级别的更改，将这些更改应用到您网站的其他区域，并确保完整记录测试、测试结果和您所做的更改。

## 监控您的操作{#section-1954311950c34637800cbd7c0711983f}

在控制实验完成并实施了相应更改后，请确保继续监控您通过（例如）查看验证量度、创建控制图表和提供功能板量度所做的更改。

如果您认为测试和所做的更改不影响原始结果，请随时准备重新测试您的假设。
