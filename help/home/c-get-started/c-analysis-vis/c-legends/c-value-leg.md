---
description: 价值图例显示定义的价值事件。
solution: Analytics
title: 值图例
topic: Data workbench
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Value legends{#value-legends}

价值图例显示定义的价值事件。

价值图例仅在 HBX 和 [!DNL Site] 应用程序中配置，但它们可以为其他应用程序配置。有关详细信息，请联系 Adobe 咨询服务部门。

在 HBX 和 [!DNL Site] 中，价值事件定义为产生商业价值的会话。例如，与特定的页面查看次数（例如，感谢订购页面或应用程序完成页面）关联的事件数据记录可能表示某个业务组织的价值事件。

借助价值事件，可以衡量和跟踪网站产生的价值量。可以评估每个事件的商业价值（以美元为单位）并回答诸如以下内容的问题：

* 网站中受益最大的途径是什么？
* 产生最大价值的推荐人或促销活动是哪些？

对于每个事件，该图例显示该事件的单位价值（每个事件的价值）以及该事件所产生的总价值。使用该图例可定义和更改价值事件以及为其分配单位价值。

下表列出了与价值事件有关的量度。

| 量度 | 描述 |
|---|---|
| 转化 | 产生商业价值的会话的百分比 |
| 价值 | 产生的商业总价值（以美元为单位） |
| 平均价值 | 每个会话产生的平均商业价值（以美元为单位） |

您可以很轻松地将访客在网站中执行的任何操作定义为一个价值事件：发布客户服务请求、完成应用、查看某一部分的内容或完成购买。每个价值事件都与访问网站上特定页面或页面集的用户相对应，并且与某个商业价值（以美元为单位）关联。例如，您可能假定访问“感谢购买”页面的每个用户产生的平均边际收益为 20 美元。那么您将为该页面定义一个价值为 20 美元的价值事件。

## 定义新的价值事件 {#section-2ea4d168336e4d2e98b22b636ed43853}

**在 HBX 或[!DNL Site]**中定义新的价值事件

在创建价值事件时，可将表示价值的网站页面从可视化拖动到价值图例。

1. 打开一个价值图例。

   ![](assets/lgd_ValueLegend.png)

1. 从流程图、URI 页面表格或页面层次视图向图例中添加价值事件：

   * 从流程图，将节点从流程图拖动到图例。
   * 从 URI 页面表格，按 Ctrl+Alt 并将页面从表格拖动到图例。
   * 从页面层次视图，单击节点（文件夹、页面或组）左侧并将其拖动到图例。
   ![](assets/client-leg.png)

   鼠标指针会显示“否”一词，直到鼠标到达图例为止。

1. 在价值图例中，为发生该事件的每个会话分配一个商业价值：

   1. In the [!DNL Value per Event] column, click the cell that corresponds to the page you have added as a value event.
   1. 键入为该事件的价值分配的美元金额，然后按 Enter。
   ![](assets/lgd_ValueLegend_Value.png)

   默认情况下，会在价值图例中显示定义为价值事件的页面的 URL。如果需要，可以双击图例中的此 URL 以进入编辑模式并重命名事件。您也可以随时编辑特定事件的价值。Data Workbench Server自动重新计算基于值事件的度量，如平均值和转化率。

至少定义一个价值事件后，“价值区段”维度将变为可用。该维度表示访客在所有会话中产生的总价值。

## 删除价值事件 {#section-25cd90a859384ca183c0fc0998f888cf}

* Right-click the desired event and click **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Data Workbench Server可计算整个数据集中的指标，这些指标可供您使用的配置文件访问。 默认情况下，[!DNL Data Workbench Server] 会在分析数据集中的所有数据上计算量度，如“值”、“值事件”、“平均值”和“转化”，即使该数据不是来自同一逻辑源也是如此。

## 导出到Microsoft Excel {#section-feaa7a8eb8124fafbc74169bebaed6d8}

有关导出窗口的信息，请参 [阅导出窗口数据](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)。
