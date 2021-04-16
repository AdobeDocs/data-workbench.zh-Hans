---
description: Insight Server (InsightServer64.exe) 允许您通过事件数据或查找数据定义自定义维度。
title: 关于扩展维度
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 55%

---

# 关于扩展维度{#about-extended-dimensions}

Insight Server (InsightServer64.exe) 允许您通过事件数据或查找数据定义自定义维度。

您定义的任何自定义维度都称为扩展维度。您可以使用它们创建可视化、构建扩展量度，或执行分析以了解与您的业务渠道相关的操作和问题。您可以在[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件中定义几种类型的扩展尺寸。

扩展维度表示日志字段值与父维度之间的关系。父维可以是任何用户定义的可计数维。 请参阅[可计数Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)。 在[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件中定义维时指定父项。 维度的父项与其级别相同。例如，如果您定义的维度父项为“会话”，则该维度将是“会话级别的维度”。

>[!NOTE]
>
>日志字段值可以来自日志([!DNL .vsl])文件或其他事件数据源中可用的固有值，也可以来自通过使用转换创建的扩展日志字段。

要向可视化添加扩展维度，可以从[!DNL Select Dimension]菜单中的扩展列表访问该维度。 例如，要向图形可视化添加扩展维度，可在工作区中右键单击，然后单击&#x200B;**[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*。 如果您要在 Data Workbench 界面内组织扩展维度的列表，可以将扩展维度移到创建的子文件夹中。请参阅《Data Workbench 用户指南》**&#x200B;的“管理界面”一章。如果您执行此操作，则子文件夹的名称也会出现在菜单中，就如同您单击“添加可视化”>“图形”>“扩展”>“&lt;*子文件夹名称*>”>“&lt;*维度名称*>”一样。

要查看为数据集用户档案定义的所有维以及每个维的缓冲区大小，请打开Data Workbench中的[!DNL Detailed Status]接口，然后单击&#x200B;**[!UICONTROL Performance]**，然后单击&#x200B;**[!UICONTROL Dimensions]**&#x200B;展开节点。 缓冲大小（控制查询时间）以 MB 为单位表示。有关[!DNL Detailed Status]接口的详细信息，请参阅《服务器管理和安装指南》。
