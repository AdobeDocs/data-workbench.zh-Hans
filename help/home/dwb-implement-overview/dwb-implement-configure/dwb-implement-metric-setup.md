---
description: 本节介绍如何在Data Workbench中创建量度。
title: 量度设置
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
exl-id: a60c08d3-f708-43be-a14f-8b7f129f3ee5
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 38%

---

# 量度设置{#metrics-setup}

本节介绍如何在Data Workbench中创建量度。

## 了解量度 {#section-f0412e851fcb4ac9886dca4003d42cec}

量度是有关客户活动的量化信息，例如查看次数、订购次数、调用次数和收入。 量度是报表的基础，可帮助您查看并理解数据关系。

量度Dimension允许您按特定级别对量度计数进行分组。 它还允许您按特定级别对量度计数进行分组。

## 创建新量度 {#section-60a413899d1b4707965e06fb5ef7fc4e}

按照以下步骤创建新量度：

1. 单击&#x200B;**工具** > **量度编辑器**。

1. 在量度编辑器中，输入新的量度名称和公式。![](assets/dwb_impl_metrics1.png)

1. 将其保存到“量度”文件夹。![](assets/dwb_impl_metrics2.png)

## 创建和编辑派生量度 {#section-ebdcd3ec652f485e90e001d694eab6d0}

使用量度编辑器按名称、公式和格式定义新量度，该量度将保存到[!DNL User\profile_name\Metrics]文件夹中以供日后使用。

1. 使用&#x200B;**管理员 > 配置文件**&#x200B;菜单选项，或通过右键单击需要在其中创建量度的文件夹的用户列，然后单击&#x200B;**创建 > 新建量度**&#x200B;来打开新的“量度编辑器”。随即会显示“量度编辑器”。

1. 在&#x200B;*Name*&#x200B;参数中，键入新量度的名称。

   >[!NOTE]
   >
   >请注意，允许使用空格 ( ) 但不允许使用下划线 (_)。此外，不能使用以下符号： + - * /

   ![](assets/dwb_impl_metrics3.png)

1. 在&#x200B;*Formula*&#x200B;参数中，键入新量度的表达式。

   >[!NOTE]
   必须在括号[内定义过滤器 ] 中。有关其他量度表达式语法规则，请参阅[量度表达式的语法。](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   此表提供了扩展量度的示例表达式。![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   输入相应的表达式后，预览行会显示新量度的值。 如果表达式中存在错误，则预览行会显示一条错误消息。

1. 右键单击并选择&#x200B;**Save**。 保存该量度时，会在计算机上的DWB *安装目录\User\profile name\Metrics*&#x200B;文件夹中创建一个表示该新量度的文件。

## 编辑现有派生量度 {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. 在“配置文件管理器”或“量度管理器”的配置文件名称列中，右键单击需要编辑的量度文件的复选标记，然后单击&#x200B;**制作本地副本**。
1. 右键单击“用户”列中量度文件的复选标记，然后单击工作台中的&#x200B;**打开**。

   >[!NOTE]
   您还可以通过右键单击可视化中任何与量度相关的区域来打开量度编辑器，以显示量度菜单。

1. 在“**量度编辑器**”中，使用&#x200B;*创建新的派生量度*&#x200B;中的步骤 2-4，根据需要编辑和保存量度定义。

   如果您希望配置文件的所有用户都能够使用您编辑的量度，则必须使用“配置文件管理器”将其发布到工作配置文件。

有关更多帮助，请参阅文档：

[量度表达式的语法](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[创建和编辑派生量度](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
