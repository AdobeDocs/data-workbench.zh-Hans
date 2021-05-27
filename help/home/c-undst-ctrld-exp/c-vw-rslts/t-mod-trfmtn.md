---
description: 现在，x-experient字段可用，您必须创建一个扩展维度以在数据集中包含x-experient字段，以便在Insight中查看结果。
solution: Analytics,Analytics
title: 修改 Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# 修改 Transformation.cfg{#modifying-transformation-cfg}

现在，x-experient字段可用，您必须创建一个扩展维度以在数据集中包含x-experient字段，以便在Insight中查看结果。

为此，必须向[!DNL Transformation.cfg]文件中添加新维度。

如果您计划运行多个实验，则还必须向[!DNL Transformation.cfg]文件中添加新的Split转换。 此Split转换将不同的实验和组名称分开，以便更容易理解信息。 为避免在以后需要添加其他实验时再次重新处理数据，即使您当前不打算运行多个实验，Adobe仍建议您添加Split转换。

以下过程包括创建新的拆分转换和扩展维。 如果不想添加Split转换，则只需跳过步骤5-7。

**修改Transformation.cfg**

1. 在[!DNL Insight]中，打开[!DNL Profile Manager]，方法是：在工作区中右键单击并单击&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在[!DNL Admin]选项卡上打开“配置文件管理”工作区。
1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Dataset]**&#x200B;以显示其内容。
1. 右键单击[!DNL Transformation.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。
1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出现[!DNL Transformation.cfg]窗口。
1. 单击&#x200B;**[!UICONTROL Transformation]**&#x200B;以显示其内容。
1. 右键单击&#x200B;**[!UICONTROL Transformations]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Split]**。
1. 按照以下示例所示，完成逗号转换的新拆分：

   ![步骤信息](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >您可以在名称字段中输入任何值。

1. 右键单击&#x200B;**[!UICONTROL Extended Dimensions]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**。
1. 完成新维度，如以下示例所示：

   ![步骤信息](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 您可以在名称字段中输入任何值。
   >* 如果不包含Split转换，则必须在[!DNL Input]字段中键入“x-experience”。


1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL Transformation.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]**&#x200B;以保存本地对工作配置文件所做的更改。

   >[!NOTE]
   >
   >数据集会立即开始重新转换。

   有关[!DNL Transformation.cfg]和扩展维度的更多信息，请参阅&#x200B;*《数据集配置指南》*。
