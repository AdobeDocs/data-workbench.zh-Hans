---
description: 您可以使用“量度编辑器”定义新的量度（称为派生量度）和编辑现有的量度定义。
solution: Analytics
title: 使用派生的指标
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用派生的指标{#work-with-derived-metrics}

您可以使用“量度编辑器”定义新的量度（称为派生量度）和编辑现有的量度定义。

有关本节和查询语言语法中提供的指标的详细信息 [，请参](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)阅《指标、维度和过滤器指南》 **。

## 创建派生量度 {#section-d57b98bf0a9940daba4920ff7efc808d}

You use a [!DNL Metric Editor] to define a new metric by name, formula, and format, which is saved to the User\*profile_name*\Metrics folder for later use.

1. Open a new [!DNL Metric Editor] using the **[!UICONTROL Admin]** > **[!UICONTROL Profile]** menu option or by right-clicking the **[!UICONTROL User]** column for the folder in which you want to create the metric and clicking **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   显示 [!DNL Metric Editor] 屏。

1. 在“名称”参数中，键入新量度的名称。

   请注意，允许使用空格 ( ) 但不允许使用下划线 (_)。此外，不能使用以下符号：

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. 在“公式”参数中，键入新量度的表达式。请注意，过滤器必须在括号内定义 [ ] 在表达式中。

   有关其他度量表达式语法规则，请参 [阅度量表达式的语法](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)。

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
   >输入适当的表达式后，预览行将显示新度量的值。 如果表达式中存在错误，则预览行会显示一条错误消息。

1. 右键单击 **[!UICONTROL (New)]** 并单击 **[!UICONTROL Save]**。

   保存度量时，将在您的计算机上的Data Workbench安装目录\User\*配置文件名称*\Metrics文件夹中创建一个表示新度量的文件。

   ![](assets/vis_MetricEditor_NewAndEditing.png)

现在，通过将新量度选择为任意内置量度，可以在当前整个配置文件中使用该新量度。若要更改量度在量度菜单中的显示顺序，请参阅[使用 Order.txt 文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

If you would like all users of the profile to use the metric that you created, you must publish it to the working profile using the [!DNL Profile Manager]. See [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## 编辑派生的指标 {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. In the [!DNL Profile Manager] or [!DNL Metrics Manager], in the *profile name* column, right-click the check mark for the metric file that you want to edit, then click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the metric file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >You also can open a [!DNL Metric Editor] by right-clicking any metric-related area within a visualization to display the metric menu. 有关详细信息，请参 [阅使用度量和维菜单](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)。

1. In the [!DNL Metric Editor], edit and save the metric definition as necessary using Steps 2-4 in [Creating New Derived Metrics](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   If you would like all users of the profile to use the metric that you edited, you must publish it to the working profile using the [!DNL Profile Manager]. See [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

