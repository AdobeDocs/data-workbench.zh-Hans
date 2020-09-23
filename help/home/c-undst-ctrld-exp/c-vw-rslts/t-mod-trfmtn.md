---
description: 现在，x-experient字段可用，您必须创建一个扩展维度以在数据集中包含x-experient字段，这允许您在Insight中视图结果。
solution: Analytics,Analytics
title: 修改 Transformation.cfg
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---


# 修改 Transformation.cfg{#modifying-transformation-cfg}

现在，x-experient字段可用，您必须创建一个扩展维度以在数据集中包含x-experient字段，这允许您在Insight中视图结果。

为此，必须向文件添加新维 [!DNL Transformation.cfg] 度。

如果您计划运行多个实验，则还必须向文件添加一个新的Split转 [!DNL Transformation.cfg] 换。 此Split转换将不同的实验和组名分开，以便更容易解释信息。 为避免在以后需要添加其他实验时再次重新处理数据，Adobe建议您添加Split转换，即使您当前不打算运行多个实验也是如此。

以下过程包括创建新的拆分转换和扩展维。 如果不想添加拆分转换，只需跳过步骤5-7。

**修改Transformation.cfg**

1. 在中 [!DNL Insight]，通过 [!DNL Profile Manager] 在工作区中右键单击并单击> **[!UICONTROL Admin]** 或打 **[!UICONTROL Profile Manager]**&#x200B;开选项卡上的“用户档案管理”工作 [!DNL Admin] 区打开。
1. 在中， [!DNL Profile Manager]单击 **[!UICONTROL Dataset]** 以显示其内容。
1. 右键单击旁边的复选标 [!DNL Transformation.cfg] 记，然后单 **[!UICONTROL Make Local]**&#x200B;击。 A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 The [!DNL Transformation.cfg] window appears.
1. Click **[!UICONTROL Transformation]** to show its contents.
1. 右键单 **[!UICONTROL Transformations]** 击，然 **[!UICONTROL Add new]** 后单击 **[!UICONTROL Split]**>。
1. 完成逗号转换的新拆分，如以下示例所示：

   ![步骤信息](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >您可以在名称字段中输入任何值。

1. 右键单 **[!UICONTROL Extended Dimensions]** 击，然 **[!UICONTROL Add new]** 后单击 **[!UICONTROL ManyToMany]**>。
1. 完成新维，如以下示例所示：

   ![步骤信息](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 您可以在名称字段中输入任何值。
   >* 如果不包括Split转换，则必须在字段中键入“x-experict” [!DNL Input] 。


1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
1. 在列 [!DNL Profile Manager]中，右键单击该复选标记 [!DNL Transformation.cfg] ，然 [!DNL User] 后单击 **[!UICONTROL Save to]** >以保 **[!UICONTROL profile name]** 存本地对工作用户档案所做的更改。

   >[!NOTE]
   >
   >数据集会立即开始重新转换。

   For more information about [!DNL Transformation.cfg] and extended dimensions, see the *Dataset Configuration Guide*.
