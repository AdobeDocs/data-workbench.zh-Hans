---
description: 即使是针对短期临时分析需求，也建议创建仪表板。
solution: Analytics
title: 创建功能板
topic: Data workbench
uuid: 5b9e9db2-d7ac-4c97-8df0-74a9e5a0c496
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 创建功能板{#creating-a-dashboard}

即使是针对短期临时分析需求，也建议创建仪表板。

>[!NOTE]
>
>只读用户无法创建仪表板。 本条仅适用于普通用户和管理员。

用户可以出于以下几个原因决定创建仪表板：

* 可以从头开始新仪表板，以便进行即时分析，而无意重用或共享仪表板。
* 可以创建新的仪表板，以执行您自己的个人分析，以便保存和重用，但不共享。
* 可以创建、保存和共享新功能板，供您和其他功能板用户访问。 无论如何，每种情况都始于同一点：空白的仪表板画布。

>[!NOTE]
>
>在开始构建功能板之前，最好将查询到百分比降低到10%或25%等低值。 这将比执行完整查询更快地从Data Workbench中提取数据样本。 由于这些采样结果的返回速度要快得多，因此在构建仪表板和分析时，它提供理想的响应性。 在准备好运行查询以完成后，可将query-to参数更新为100%。 有关调整查询完成的信息，请参 [阅查询到参数](../../../home/c-adobe-data-workbench-dashboard/c-dashboards/c-query-to-parameter.md#concept-33db106e28bc4108bca9e8d0a440d323)。

要创建新功能板，请在“功能板” **[!UICONTROL New]** 菜单下选择。

![](assets/new_dashboard.png)

您将看到一个空白的仪表板画布，该画布可根据您的分析需求添加和配置可视化。 在您工作时，在保存之前，服务器上不会更新任何内容。

接下来，决定要显示哪类数据以及要如何显示它。 它通常有助于从表可视化开始查看原始数据，然后根据需要构建其他图表。 有关如何添加和配置可视化的详细信息，请参阅创 [建可视化](../../../home/c-adobe-data-workbench-dashboard/c-visualizations/t-creating-visualizations.md#task-c6f1d20fa2484aeeb9a8487625054ecf)。 在添加和配置可视化以构建功能板后，您将最终得到以下结果：

![](assets/after_configure.png)

此时，您只需执行分析并放弃功能板，或选择将功能板保存到服务器以重复使用和／或共享。 有关如何与功能板进行交互以执行分析的信息，请参阅功能板 [中的选择部分](../../../home/c-adobe-data-workbench-dashboard/c-making-selections-within-the-dashboard/c-making-selections-within-the-dashboard.md#concept-0989862de0044cc4bbfd7f4441275fc4)。
