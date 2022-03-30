---
description: 现在，x-experient字段可用，您必须创建一个扩展维度以在数据集中包含x-experient字段，以便在Insight中查看结果。
solution: Analytics
title: 修改 Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# 修改 Transformation.cfg{#modifying-transformation-cfg}

现在，x-experient字段可用，您必须创建一个扩展维度以在数据集中包含x-experient字段，以便在Insight中查看结果。

为此，您必须在 [!DNL Transformation.cfg] 文件。

如果您计划运行多个实验，则还必须向 [!DNL Transformation.cfg] 文件。 此Split转换将不同的实验和组名称分开，以便更容易理解信息。 为避免在以后需要添加其他实验时再次重新处理数据，即使您当前不打算运行多个实验，Adobe仍建议您添加Split转换。

以下过程包括创建新的拆分转换和扩展维。 如果不想添加Split转换，则只需跳过步骤5-7。

**修改Transformation.cfg**

1. 在 [!DNL Insight]，打开 [!DNL Profile Manager] 右键单击工作区并单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在 [!DNL Admin] 选项卡。
1. 在 [!DNL Profile Manager]，单击 **[!UICONTROL Dataset]** 以显示其内容。
1. 右键单击旁边的复选标记 [!DNL Transformation.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 的 [!DNL Transformation.cfg] 窗口。
1. 单击 **[!UICONTROL Transformation]** 以显示其内容。
1. 右键单击 **[!UICONTROL Transformations]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. 按照以下示例所示，完成逗号转换的新拆分：

   ![步骤信息](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >您可以在名称字段中输入任何值。

1. 右键单击 **[!UICONTROL Extended Dimensions]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. 完成新维度，如以下示例所示：

   ![步骤信息](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 您可以在名称字段中输入任何值。
   >* 如果不包含Split转换，则必须在 [!DNL Input] 字段。


1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.
1. 在 [!DNL Profile Manager]，右键单击的复选标记 [!DNL Transformation.cfg] 在 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > **[!UICONTROL profile name]** 以保存本地对工作配置文件所做的更改。

   >[!NOTE]
   >
   >数据集会立即开始重新转换。

   有关 [!DNL Transformation.cfg] 和扩展维度，请参阅 *数据集配置指南*.
