---
description: Insight Server (InsightServer64.exe) 允许您通过事件数据或查找数据定义自定义维度。
solution: Analytics
title: 关于扩展维度
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 关于扩展维度{#about-extended-dimensions}

Insight Server (InsightServer64.exe) 允许您通过事件数据或查找数据定义自定义维度。

您定义的任何自定义维度都称为扩展维度。您可以使用它们创建可视化、构建扩展量度，或执行分析以了解与您的业务渠道相关的操作和问题。You can define several types of extended dimensions in the [!DNL Transformation.cfg] file or in [!DNL Transformation Dataset Include] files.

扩展维度表示日志字段值与父维度之间的关系。父维可以是任何用户定义的可计数维。 请参 [阅可计数维](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)。 You specify the parent when defining the dimension in the [!DNL Transformation.cfg] file or a [!DNL Transformation Dataset Include] file. 维度的父项与其级别相同。例如，如果您定义的维度父项为“会话”，则该维度将是“会话级别的维度”。

>[!NOTE]
>
>The log field values can come from the inherent values available in the log ( [!DNL .vsl]) files or other event data sources or from extended log fields created through the use of transformations.

To add an extended dimension to a visualization, you access it from the Extended list within the [!DNL Select Dimension] menu. For example, to add an extended dimension to a graph visualization, you would right-click within the workspace and click **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. 如果您要在 Data Workbench 界面内组织扩展维度的列表，可以将扩展维度移到创建的子文件夹中。请参阅《Data Workbench 用户指南》**&#x200B;的“管理界面”一章。如果您执行此操作，则子文件夹的名称也会出现在菜单中，就如同您单击“添加可视化”>“图形”>“扩展”>“&lt;*子文件夹名称*>”>“&lt;*维度名称*>”一样。

To see all the dimensions that have been defined for your dataset profile and the buffer size for each, open the [!DNL Detailed Status] interface in data workbench and click **[!UICONTROL Performance]**, then **[!UICONTROL Dimensions]** to expand the nodes. 缓冲大小（控制查询时间）以 MB 为单位表示。For more information about the [!DNL Detailed Status] interface, see the Server Administration and Installation guide.
