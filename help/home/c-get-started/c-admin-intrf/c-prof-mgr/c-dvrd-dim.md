---
description: 您使用Data Workbench创建的新维（称为派生维）是客户端维。
solution: Analytics
title: 使用派生维
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用派生维{#work-with-derived-dimensions}

您使用Data Workbench创建的新维（称为派生维）是客户端维。

Instead of defining these dimensions during the dataset construction and update process (in the [!DNL Transformation.cfg] file) on your Data Workbench server computers, derived dimensions are created and stored individually as [!DNL .dim] files in a profile. 因此，您可以更改现有的派生维度和创建新的派生维度，而无需重新处理您的数据集。

>[!NOTE]
>
>有关本节中提供的维的详细信息，请参阅相应的Data Workbench应用程序指南。

有关数据集配置和更新进程的详细信息，请参阅《数据集配置指南》**。

## 创建派生的维 {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

若要创建派生维度，可以复制并修改现有维度或保存可视化中的维度。

## 从现有维创建派生维 {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

用户通常希望基于现有维度创建新时间维度。例如，您可以基于现有的“最近 7 天”维度创建一个新的“最近 5 天”维度。

1. In the [!DNL Profile Manager], in the *profile name* column, right-click the check mark for a dimension that is similar to the dimension that you want to create and click **[!UICONTROL Copy]**.

   For example, to copy the [!DNL Last 7 Days.dim] from the Reporting folder of the [!DNL Traffic] profile, you right-click the check mark for the file name in the [!DNL Traffic] column and click **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Right-click in the [!DNL User] column for the folder in which you want to store the copied dimension and click **[!UICONTROL Paste]**.

   The dimension appears in the selected Dimensions folder with a check mark in the [!DNL User] column.

1. To rename the new dimension, right-click its check mark in the [!DNL User] column and type the new name in the [!DNL File] field.
1. 在右键单击菜单中，单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 将显示维度的定义参数。
1. 根据需要修改参数以定义新维度。

   对于时间维度，您最可能需要修改的只有 Count（计数）和 Range（范围）参数。

1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

   If you would like all users of a profile to use the dimension that you created, you must upload it to the profile using the [!DNL Profile Manager]. 有关详细信息，请参 [阅将文件发布到工作配置文件](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

现在，通过将新维度选择为任意内置维度，可以在当前整个配置文件中使用该新维度。

## 从可视化中保存维度 {#section-84cfe5e9ccb640afa2ee4e2da2682757}

您可以保存流程图和区段中的扩展维度。有关从流程图保存维度的步骤，请参阅[从流程图保存维度](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)。有关保存区段维度的步骤，请参阅 [第](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) 82页上的创建区段维。

## 将区段另存为维 {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

您还可以将已定义的区段另存为维度。有关步骤，请参阅 [重用区段可视化](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Edit an existing derived dimension {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n the [!DNL Profile Manager], in the *profile name* column, right-click the check mark for the dimension file that you want to edit and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the dimension file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. 根据需要填写各个参数。有关详细信息，请联系 Adobe 咨询服务部门。
1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

   If you would like all users of a profile to use the modified dimension, you must upload it to the profile using the [!DNL Profile Manager]. 有关详细信息，请参 [阅将文件发布到工作配置文件](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

