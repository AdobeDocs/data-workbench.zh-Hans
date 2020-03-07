---
description: 本节介绍如何在Data Workbench中创建量度。
title: 指标设置
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# 指标设置{#metrics-setup}

本节介绍如何在Data Workbench中创建量度。

## 了解指标 {#section-f0412e851fcb4ac9886dca4003d42cec}

指标是有关客户活动的量化信息，如查看次数、订单数、拨叫次数和收入。 量度是报表的基础，可帮助您查看并理解数据关系。

“度量维度”允许您按特定级别对度量计数进行分组。 它还允许您按特定级别对度量计数进行分组。

## 创建新指标 {#section-60a413899d1b4707965e06fb5ef7fc4e}

请按照以下步骤创建新量度：

1. 单击 **工具** > **度量编辑器**。

1. 在量度编辑器中，输入新的量度名称和公式。 ![](assets/dwb_impl_metrics1.png)

1. 将其保存到“度量”文件夹。 ![](assets/dwb_impl_metrics2.png)

## 创建和编辑派生量度 {#section-ebdcd3ec652f485e90e001d694eab6d0}

Use a Metric Editor to define a new metric by name, formula, and format, which is saved to the [!DNL User\profile_name\Metrics] folder for later use.

1. 使用&#x200B;**管理员 > 配置文件**&#x200B;菜单选项，或通过右键单击需要在其中创建量度的文件夹的用户列，然后单击&#x200B;**创建 > 新建量度**&#x200B;来打开新的“量度编辑器”。随即会显示“量度编辑器”。

1. In the *Name* parameter, type a name for the new metric.

   >[!NOTE]
   >
   >请注意，允许使用空格 ( ) 但不允许使用下划线 (_)。此外，不能使用以下符号： + - * /

   ![](assets/dwb_impl_metrics3.png)

1. In the *Formula* parameter, type an expression for the new metric.

   >[!NOTE]
   必须在括号内定义滤镜 [ ] 在表达式中。 有关其他度量表达式语法规则，请参 [阅度量表达式的语法。](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   This table provides sample expressions for extended metrics. ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   输入适当的表达式后，预览行将显示新度量的值。 如果表达式中存在错误，则预览行会显示一条错误消息。

1. 右键单击并选择“保 **存”**。 When you save the metric, a file representing the new metric is created on your computer in the DWB *Installation directory \User\profile name\Metrics* folder.

## 编辑现有派生量度 {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. 在“配置文件管理器”或“量度管理器”的配置文件名称列中，右键单击需要编辑的量度文件的复选标记，然后单击&#x200B;**制作本地副本**。
1. Right-click the check mark for the metric file in the User column and click **Open** from the workbench.

   >[!NOTE]
   您还可以通过右键单击可视化中任何与量度相关的区域来打开度量编辑器，以显示度量菜单。

1. 在“**量度编辑器**”中，使用&#x200B;*创建新的派生量度*&#x200B;中的步骤 2-4，根据需要编辑和保存量度定义。

   如果您希望配置文件的所有用户都能够使用您编辑的量度，则必须使用“配置文件管理器”将其发布到工作配置文件。

请参阅文档以获取更多帮助：

[量度表达式的语法](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[创建和编辑派生量度](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
