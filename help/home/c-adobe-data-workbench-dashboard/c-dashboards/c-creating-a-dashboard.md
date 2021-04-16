---
description: 即使是针对短期临时分析需求，也建议创建仪表板。
title: 创建功能板
uuid: 5b9e9db2-d7ac-4c97-8df0-74a9e5a0c496
exl-id: bd51d4c0-bcf2-4ba6-8b32-de06c74f359f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 1%

---

# 创建功能板{#creating-a-dashboard}

即使是针对短期临时分析需求，也建议创建仪表板。

>[!NOTE]
>
>只读用户无法创建仪表板。 此部分仅适用于普通用户和管理员。

用户可出于以下几个原因决定创建仪表板:

* 可以从头开始创建新的仪表板，以便实时分析，无意重用或共享仪表板。
* 可以创建新仪表板，以执行您自己想要保存和重用（但不共享）的个人分析。
* 可以创建、保存和共享新仪表板，供您和其余仪表板用户访问。 无论如何，每种情景都在同一点开始:空白仪表板画布。

>[!NOTE]
>
>在开始构建仪表板之前，最好将查询到百分比降低到较低值，如10%或25%。 这将比执行完整查询更快地从Data Workbench中提取数据样本。 由于这些采样结果的返回速度要快得多，因此在构建仪表板和分析时，它提供了理想的响应性。 准备好运行查询以完成后，您可以将“查询到”参数更新为100%。 有关调整查询完成的信息，请参阅[查询到参数](../../../home/c-adobe-data-workbench-dashboard/c-dashboards/c-query-to-parameter.md#concept-33db106e28bc4108bca9e8d0a440d323)。

要创建新仪表板，请在“仪表板”菜单下选择&#x200B;**[!UICONTROL New]**。

![](assets/new_dashboard.png)

您将看到一个空白的仪表板画布，该画布准备根据您的分析需求添加和配置可视化。 在您工作时，在您保存之前，服务器上不会更新任何内容。

接下来，确定要显示的数据类型和显示方式。 通常，它有助于开始表可视化以查看原始数据，然后构建出适合其他图表。 有关如何添加和配置可视化的详细信息，请参阅[创建可视化](../../../home/c-adobe-data-workbench-dashboard/c-visualizations/t-creating-visualizations.md#task-c6f1d20fa2484aeeb9a8487625054ecf)。 在添加和配置可视化以构建仪表板后，您将最终得到以下结果：

![](assets/after_configure.png)

此时，您只需执行分析并放弃仪表板，或选择将仪表板保存到服务器以重复使用和/或共享。 有关如何与仪表板交互以执行分析的信息，请参阅[在仪表板中进行选择](../../../home/c-adobe-data-workbench-dashboard/c-making-selections-within-the-dashboard/c-making-selections-within-the-dashboard.md#concept-0989862de0044cc4bbfd7f4441275fc4)部分。
