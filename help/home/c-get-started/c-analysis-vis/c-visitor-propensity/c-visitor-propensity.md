---
description: 通过倾向评分，您可以基于客户成功转化或完成指定事件的可能性来定义客户。通过该功能，您可以在执行某个流程或发起某项促销活动之前，最大程度地了解工作的潜在影响。
title: 倾向评分
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 86%

---

# 倾向评分{#propensity-scoring}

通过倾向评分，您可以基于客户成功转化或完成指定事件的可能性来定义客户。通过该功能，您可以在执行某个流程或发起某项促销活动之前，最大程度地了解工作的潜在影响。

## 倾向评分的价值 {#section-c51ece66effc42de9b754f0f46027c1b}

倾向评分可让您执行数据发现，以便识别出数据中存在的隐藏行为或模式。具体而言，倾向评分可帮助您使用更加专注和客观的方式，而不是通过简单的划分或过滤来识别相似客户群。此外，倾向评分允许您设置预测功能，以识别公司的高价值客户的行为。

确定高价值受众后，您可以让他们参与互动以获得最佳效果。例如，如果您是企业对企业的公司，您应该对自己的销售电话线索进行打分并识别其线下转化的可能性。由于每个潜在客户都会增加成本，因此，创造一种激励机制来识别最有可能转化为销售的潜在客户是集中资源的最有效和最便宜的方法。

倾向评分不仅能够识别最能对特定评分进行预测的因素，或者提高事件发生的概率，也可以应用于回答特定问题：客户是否会转化？客户是否会回复电子邮件？客户是否会再次购买？通过倾向评分，您可以回答这些问题并识别具有相应操作倾向的访客，然后可以进行相应设置和评分。

此外，您还可以使用过滤器定义要使用可选&#x200B;**[!UICONTROL Training Filter]**&#x200B;功能进行评分的访客子集。 如果没有应用任何过滤器，则所有访客均为打分的目标。

## 倾向评分可视化的功能  {#section-28413bc7d33b42c59cecb427c1c5a3fa}

要打开倾向评分可视化，请单击&#x200B;**[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**。

![](assets/propensity_visualization_GO.png)

倾向评分可视化包括可从其工具栏访问的以下功能：

| 工具栏功能 | 描述 |
|---|---|
| 开始 | 在设置参数后，点击运行得分程序。 |
| 重置 | 清除可视化中的所有设置。 |
| 载入 | 载入之前创建的 ScoreDim，它可以允许您更改和/或重建得分模型。 |
| 保存 | 将倾向评分可视化保存为 Dim 文件，以便根据需要访问和打开。 |
| Submit | 提交得分任务，以便服务器侧进行处理。 |
| 选项 | 设置“训练过滤器”以限制访客的子集。默认过滤器为&#x200B;**[!UICONTROL Train on Everyone]**，但您可以通过选择工作区或使用&#x200B;**[!UICONTROL Filter Editor]**&#x200B;构建过滤器来更改它。 |
| 设置目标 | 设置“因变量”。 |
| 指标 | 添加量度作为“独立变量”。 |
| 元素 | 使用`<Ctrl>` + `<Alt>`键从Dimension表中拖动Dimension元素。 |

**另请参阅**:

* [增益和提升图](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)。 这些视图可以从完整的评分模型或[!DNL Add Visualization> Predictive Analytics > Scoring.]打开
* [模型查看器](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd)。这些视图可以从完整的评分模型或[!DNL Add Visualization> Predictive Analytics > Scoring.]打开
* [复杂滤镜描述](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff)功能。

## 使用倾向评分可视化 {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **定义一个或多个过滤器来定义要打分的访客群**。此可选&#x200B;**[!UICONTROL Training Filter]**&#x200B;允许您根据所选条件目标访客。 如果没有应用任何训练过滤器，则所有访客均为打分的目标。如果设置了训练过滤器，则打分结果对于定义的访客群来说很有意义，虽然仍会为每个访客给出得分。
* **识别积极访客**。要定义因变量，请指定目标过滤器，它可以识别匹配所需结果的积极访客。这可以像“收入 > $10”一样简单，也可以是更为复杂的过滤器。
* **目标过滤器不允许与训练过滤器相同**。在逻辑上，目标过滤器应该是训练过滤器的补充，以便为访客群的积极子集打分。
* **选择兴趣变量（独立变量）作为倾向评分算法的输入**。可以是“量度”或“维度”的单独元素。倾向评分将开始预处理，就像 [访客聚类](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). 系统开始捕捉指定数量的示例，这些示例与以前设置的训练过滤器（如果有）的定义匹配。目前，示例大小设为得分人群的 10%（由训练过滤器定义），最小为 20000，最大为 100000，并与得分人群大小绑定。

* 得分变量含有范围从 0% 到 100% 的元素，用于确定访客匹配“目标”变量的可能性。
