---
description: 延迟表格可视化是包含延迟维度的表格，延迟维度是一种用于测量自某个特定事件发生后已经过去的时间的派生维度。
solution: Analytics
title: 延迟表
topic: Data workbench
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Latency tables{#latency-tables}

延迟表格可视化是包含延迟维度的表格，延迟维度是一种用于测量自某个特定事件发生后已经过去的时间的派生维度。

定义事件的方法是通过在一个或多个可视化中进行选择，然后使用“设置事件”上下文菜单选项将这些选择设置为事件。延迟表格对于跟踪与某个促销活动有关的活动或跟踪您正在查找时间相关性的特定客户订单特别有用。

在 [!DNL Site] 中，延迟表格提供有关该事件发生 7 天前后发生的访客会话的信息，但您可以将延迟表格配置为提供有关不同的可计数维度和时间维度的信息。See [Configuring Latency Tables](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

父维度的元素（如会话）就是您所选择的特定事件的一部分，它们的延迟为零。所有其他元素分配的延迟反映了与该事件的距离（在相应的时间维度中）。

以下示例演示了如何使用延迟表格。

**确定与营销活动相关的价值事件**

例如，您希望跟踪客户对特定广告活动进行响应前后 7 天的客户活动。若要查看特定广告活动的延迟，应将感兴趣的活动设置为延迟表格的事件。

下面工作区中的延迟基于促销活动 11566（响应该活动的会话）的选择。

![](assets/vis_Latency.png)

“+0 天”的延迟标识响应促销活动 11566 的会话，以及在同一天发生的相同客户的所有其他会话。

“-2 天”的延迟标识客户响应该活动之前 2 天发生的相同客户的会话。

“+7 天”的延迟标识客户响应该活动之后 7 天发生的相同客户的会话。

除了以下部分中列出的过程之外，您还可以执行可在表格中执行的所有相同任务，如对元素进行排序、掩盖元素、添加系列图例、导出数据等。有关详细信息，请参阅 [表格](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## 创建延迟表 {#section-31a03031d9854ef7acc2462d4f37678d}

若要创建延迟表格，您可以先进行选择，然后将该选择设置为要跟踪其延迟的事件。

1. 右键单击工作区，然后打开所需的可视化，该可视化必须基于用于配置延迟表格的可计数维度。

   例如，在 [!DNL Site] 中，可视化需要基于会话。

1. 打开一个空白的延迟表格。
1. 在工作区中进行选择。
1. Right-click within the latency table and click **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>除非将选择另存为延迟维，否则您选择的事件不会持续。 有关步骤，请参阅[重用延迟维度](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46)。

## 重用延迟表 {#section-05f741169d204213b6537dce553e4f73}

如果您想再次使用同一个延迟表格，则可以将该延迟表格保存在本地，或者如果您拥有适当的权限，则可以将其保存到服务器，以便特定配置文件的所有用户都可以访问。

**保存延迟表格以便在其他工作区中使用**

1. Right-click the top border of the visualization and click **[!UICONTROL Save]**. The [!DNL Save] window appears. 默认的保存位置是User\*配置文件名称*\Work文件夹。
1. In the [!DNL File name] field, type a descriptive name for the visualization and click **[!UICONTROL Save]**.

**检索保存的延迟表格**

1. 在工作区中右键单击，然后单击 **[!UICONTROL Open]** > **[!UICONTROL File]**。 The [!DNL Open Visualization] window appears.
1. 导航到您保存的延迟表格。
1. Select the latency table visualization file ( [!DNL *.vw]) and click **[!UICONTROL Open]**.

## 重用延迟维度 {#section-29c6483bf9ba476fb1c24ad1df253f46}

如果您想再次使用同一个延迟维度，则可以将该延迟维度保存在本地，或者如果您拥有适当的权限，则可以将其保存到服务器，以便特定配置文件的所有用户都可以访问。

Any latency dimensions that you create are saved in the profile’s Dimensions directory and are available in the [!DNL Change Dimension] drop-down list within Data Workbench.

**保存延迟维度以便在其他工作区中使用**

1. Right-click the [!DNL Latency] column label or one of its elements and click **[!UICONTROL Save Dimension]**. The [!DNL Save Dimension As] window appears.
1. 在 Dimensions 目录中选择或创建相应的子目录。
1. 在字 [!DNL File name] 段中，键入维的描述性名称(例如， [!DNL Latency for Campaign 11565.dim])并单击 **[!UICONTROL Save]**。

**检索保存的延迟维度**

1. 在工作区中右键单击，然后单击 **[!UICONTROL Open]** > **[!UICONTROL File]**。 The [!DNL Open Visualization] window appears.
1. 导航到您保存在User\*配置文件名称*\Dimensions文件夹中的延迟可视化。
1. Select the latency dimension file ( [!DNL *.dim]) and click **[!UICONTROL Open]**.

## 导出到Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

有关导出窗口的信息，请参 [阅导出窗口数据](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)。

## Export to a TSV file {#section-fd921f351c994ed0a94f63d3bd5b5a87}

有关导出窗口的信息，请参 [阅导出窗口数据](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)。
