---
description: 您可以使用“量度编辑器”定义新的量度（称为派生量度）和编辑现有的量度定义。
title: 使用派生量度
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 36%

---

# 使用派生量度{#work-with-derived-metrics}

您可以使用“量度编辑器”定义新的量度（称为派生量度）和编辑现有的量度定义。

有关本节和[查询语言语法](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)中提供的量度的详细信息，请参阅&#x200B;*量度、Dimension和过滤器指南*。

## 创建派生量度{#section-d57b98bf0a9940daba4920ff7efc808d}

可使用[!DNL Metric Editor]按名称、公式和格式定义新量度，该量度将保存到User\*用户档案_name*\Metrics文件夹中供以后使用。

1. 使用&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile]**&#x200B;菜单选项或右键单击要在其中创建量度的文件夹的&#x200B;**[!UICONTROL User]**&#x200B;列，然后单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL New Metric]**，打开新[!DNL Metric Editor]。

   将显示[!DNL Metric Editor]。

1. 在“名称”参数中，键入新量度的名称。

   请注意，允许使用空格 ( ) 但不允许使用下划线 (_)。此外，不能使用以下符号：

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. 在“公式”参数中，键入新量度的表达式。请注意，过滤器必须在括号[中定义 ] 表达式。

   有关其他量度表达式语法规则，请参阅[量度表达式的语法](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)。

   下表提供了扩展量度的示例表达式。

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 扩展量度名称 </th> 
      <th colname="col2" class="entry"> 表达式 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Percent First Sessions（会话数量为 1 的会话百分比） </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessions [Session_Number="1"]/Sessions</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Conversion First Sessions（会话数量为 1 的会话转化） </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Conversion [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Average Value Per Visitor（每个访客的平均值） </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Value/Visitors</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >输入适当的表达式后，预览行将显示新量度的值。 如果表达式中存在错误，则预览行会显示一条错误消息。

1. 右键单击&#x200B;**[!UICONTROL (New)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   保存该量度时，会在计算机上的Data Workbench安装目录\User\*用户档案名称*\Metrics文件夹中创建一个表示新量度的文件。

   ![](assets/vis_MetricEditor_NewAndEditing.png)

现在，通过将新量度选择为任意内置量度，可以在当前整个配置文件中使用该新量度。若要更改量度在量度菜单中的显示顺序，请参阅[使用 Order.txt 文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

如果您希望用户档案的所有用户都使用您创建的量度，则必须使用[!DNL Profile Manager]将其发布到工作用户档案。 请参阅[将文件发布到您的工作用户档案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

## 编辑派生量度{#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. 在[!DNL Profile Manager]或[!DNL Metrics Manager]的&#x200B;*用户档案名称*&#x200B;列中，右键单击要编辑的量度文件的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。
1. 右键单击[!DNL User]列中量度文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。

   >[!NOTE]
   >
   >您还可以通过右键单击可视化中任何与量度相关的区域来打开[!DNL Metric Editor]以显示量度菜单。 有关详细信息，请参阅[使用量度和Dimension菜单](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)。

1. 在[!DNL Metric Editor]中，使用[创建新派生量度](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)中的步骤2-4，根据需要编辑和保存量度定义。

   如果您希望用户档案的所有用户都使用您编辑的量度，则必须使用[!DNL Profile Manager]将其发布到工作用户档案。 请参阅[将文件发布到您的工作用户档案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
