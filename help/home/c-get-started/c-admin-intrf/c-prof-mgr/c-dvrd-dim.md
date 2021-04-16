---
description: 您使用Data Workbench创建的新维（称为派生维）是客户端维。
title: 使用派生维度
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 34%

---

# 使用派生维度{#work-with-derived-dimensions}

您使用Data Workbench创建的新维（称为派生维）是客户端维。

派生维度不是在Data Workbench服务器计算机上的数据集构建和更新过程（在[!DNL Transformation.cfg]文件中）中定义这些维度，而是作为[!DNL .dim]文件单独创建并存储在用户档案中。 因此，您可以更改现有的派生维度和创建新的派生维度，而无需重新处理您的数据集。

>[!NOTE]
>
>有关本节中提供的维度的详细信息，请参阅相应的Data Workbench应用程序指南。

有关数据集配置和更新进程的详细信息，请参阅《数据集配置指南》**。

## 创建派生维度{#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

若要创建派生维度，可以复制并修改现有维度或保存可视化中的维度。

## 从现有维{#section-f46c2d3ab0a5416c98d6e79d18d99fa1}创建派生维

用户通常希望基于现有维度创建新时间维度。例如，您可以基于现有的“最近 7 天”维度创建一个新的“最近 5 天”维度。

1. 在[!DNL Profile Manager]的&#x200B;*用户档案名称*&#x200B;列中，右键单击与要创建的维相似的维的复选标记，然后单击&#x200B;**[!UICONTROL Copy]**。

   例如，要从[!DNL Traffic]用户档案的报告文件夹中复制[!DNL Last 7 Days.dim]，请右键单击[!DNL Traffic]列中文件名的复选标记，然后单击&#x200B;**[!UICONTROL Copy]**。

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. 右键单击要存储复制维度的文件夹的[!DNL User]列，然后单击&#x200B;**[!UICONTROL Paste]**。

   该Dimension显示在选定的维文件夹中，并在[!DNL User]列中带有复选标记。

1. 要重命名新维，请在[!DNL User]列中右键单击其复选标记，并在[!DNL File]字段中键入新名称。
1. 在右键单击菜单中，单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 将显示维度的定义参数。
1. 根据需要修改参数以定义新维度。

   对于时间维度，您最可能需要修改的只有 Count（计数）和 Range（范围）参数。

1. 要保存文件，请右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   如果您希望某个用户档案的所有用户都使用您创建的维度，则必须使用[!DNL Profile Manager]将其上传到用户档案。 有关详细信息，请参阅[将文件发布到您的工作用户档案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

现在，通过将新维度选择为任意内置维度，可以在当前整个配置文件中使用该新维度。

## 保存可视化{#section-84cfe5e9ccb640afa2ee4e2da2682757}中的维度

您可以保存流程图和区段中的扩展维度。有关从流程图保存维度的步骤，请参阅[从流程图保存维度](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)。有关保存区段维度的步骤，请参阅第82页上的[创建区段Dimension](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)。

## 将区段保存为维{#section-7c443cf1ac5a44659623cabb9e0c1ab8}

您还可以将已定义的区段另存为维度。有关步骤，请参阅 [重用区段可视化](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## 编辑现有派生维度{#section-3a82c604bf1c4d369770556d268808b2}

1. I

   在[!DNL Profile Manager]中，在&#x200B;*用户档案名称*&#x200B;列中，右键单击要编辑的维度文件的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。
1. 右键单击[!DNL User]列中维度文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。
1. 根据需要填写各个参数。有关详细信息，请联系 Adobe 咨询服务部门。
1. 要保存文件，请右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   如果希望某个用户档案的所有用户都使用修改后的维度，则必须使用[!DNL Profile Manager]将其上传到用户档案。 有关详细信息，请参阅[将文件发布到您的工作用户档案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
