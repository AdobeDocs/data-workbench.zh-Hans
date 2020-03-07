---
description: 通过倾向评分，您可以基于客户成功转化或完成指定事件的可能性来定义客户。通过该功能，您可以在执行某个流程或发起某项促销活动之前，最大程度地了解工作的潜在影响。
solution: Analytics
title: 倾向评分
topic: Data workbench
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 倾向评分{#propensity-scoring}

通过倾向评分，您可以基于客户成功转化或完成指定事件的可能性来定义客户。通过该功能，您可以在执行某个流程或发起某项促销活动之前，最大程度地了解工作的潜在影响。

## 倾向评分的值 {#section-c51ece66effc42de9b754f0f46027c1b}

倾向评分可让您执行数据发现，以便识别出数据中存在的隐藏行为或模式。特别需要指出的是，倾向评分使用更为集中和具针对性的方法（而不是简单分段或过滤）来帮助您识别相似客户的聚类。此外，倾向评分可让您设置预测功能来识别贵公司高价值客户的行为。

当您识别出高价值受众后，您可以吸引他们以取得最佳效果。例如，如果您是企业对企业的公司，您应该对自己的销售电话线索进行打分并识别其线下转化的可能性。由于每个线索均会增加成本，创建激励机制，以识别出最有可能转化销售的潜在客户是集中资源最有效和最经济的方式。

倾向评分不但提供了识别最能预测特定得分的因素或增加活动发生可能性的功能，它还能用于回答指定问题：客户会转化吗？客户会回应电子邮件吗？客户会重复购买吗？倾向评分可让您回答这些问题，并识别出具有可随后进行设置和打分的行为倾向的访客。

In addition, you can use filters to define a subset of visitors to be scored using the optional **[!UICONTROL Training Filter]** feature. 如果没有应用任何过滤器，则所有访客均为打分的目标。

## 倾向评分可视化的功能 {#section-28413bc7d33b42c59cecb427c1c5a3fa}

要打开倾向评分可视化，请单击 **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**。

![](assets/propensity_visualization_GO.png)

倾向评分可视化包括可从其工具栏访问的以下功能：

| 工具栏功能 | 描述 |
|---|---|
| 开始 | 在设置参数后，点击运行得分程序。 |
| 重置 | 清除可视化中的所有设置。 |
| 载入 | 载入之前创建的 ScoreDim，它可以允许您更改和/或重建得分模型。 |
| 保存 | 将倾向评分可视化保存为 Dim 文件，以便根据需要访问和打开。 |
| 提交 | 提交得分任务，以便服务器侧进行处理。 |
| 选项 | 设置“训练过滤器”以限制访客的子集。The default filter is **[!UICONTROL Train on Everyone]**, but you can change it by making workspace selections or building a filter using the **[!UICONTROL Filter Editor]**. |
| 设置目标 | 设置“因变量”。 |
| 量度 | 添加量度作为“独立变量”。 |
| 元素 | Drag Dimension elements using the `<Ctrl>` + `<Alt>` keys from Dimension tables. |

**另请参阅**：

* The[增益图和提升图](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)。可以从完整的评分模型或 [!DNL Add Visualization> Predictive Analytics > Scoring.]
* [模型查看器](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd)。可以从完整的评分模型或 [!DNL Add Visualization> Predictive Analytics > Scoring.]
* The [Complex Filter Description](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) feature.

## 使用倾向评分可视化 {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **定义一个或多个过滤器来定义要打分的访客群**。This optional **[!UICONTROL Training Filter]** lets you target visitors based on selected criteria. 如果没有应用任何训练过滤器，则所有访客均为打分的目标。如果设置了训练过滤器，则打分结果对于定义的访客群来说很有意义，虽然仍会为每个访客给出得分。
* **识别积极访客**。要定义因变量，请指定目标过滤器，它可以识别匹配所需结果的积极访客。这可以像“收入 > $10”一样简单，也可以是更为复杂的过滤器。
* **目标过滤器不允许与训练过滤器相同**。在逻辑上，目标过滤器应该是训练过滤器的补充，以便为访客群的积极子集打分。
* **选择兴趣变量（独立变量）作为倾向评分算法的输入**。可以是“量度”或“维度”的单独元素。倾向评分将开始预处理，就像 [访客聚类](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). 系统开始捕捉指定数量的示例，这些示例与以前设置的训练过滤器（如果有）的定义匹配。目前，示例大小设为得分人群的 10%（由训练过滤器定义），最小为 20000，最大为 100000，并与得分人群大小绑定。

* 得分变量含有范围从 0% 到 100% 的元素，用于确定访客匹配“目标”变量的可能性。

