---
description: 您可以创建由任意可计数维度的元素所组成的区段，然后将该区段的数据批量输出或持续实时输出至以制表符分隔的文件。
title: 配置区段以供导出
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 70%

---

# 配置区段以供导出{#configure-segments-for-export}

{{eol}}

您可以创建由任意可计数维度的元素所组成的区段，然后将该区段的数据批量输出或持续实时输出至以制表符分隔的文件。

每当您导出区段时，可输出此区段内包含的所有维度元素所对应的量度或维度数据。您可以控制输出数据的格式，以便其他系统能够轻松加载此数据。

>[!NOTE]
>
>无法导出报表维度，因为它们使用 [!DNL report time.metric] 文件以供参考。 作为解决方案，如果在配置文件中放置一个硬编码的 [!DNL report time.metric]，则区段导出可以将它用作报表维度的引用点。但是，[!DNL report time.metric] 不会自动根据配置文件的“截至”时间进行更新，因此当您想要更改报表维度引用时，必须更改硬编码的 [!DNL report time.metric] 文件。

要配置导出区段，必须打开并编辑 [!DNL .export] 文件。

1. 在 [!DNL Profile Manager]，请单击 **[!UICONTROL Export]** 目录 [!DNL File] 列来显示其内容。

       如果 Export 目录不存在，请按照以下步骤创建该目录：
   
   1. 导航到您的Data Workbench安装目录。
   1. 打开您正在使用的配置文件目录。
   1. 在 Profile 目录中创建一个名为“Export”的新目录。

1. 在 [!DNL Profile Manager]，右键单击 [!DNL User] 列，然后单击 **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   名为的文件 [!DNL New Segment Export.export] 显示在 [!DNL File] 列。

1. 在 [!DNL User] 列，然后在“文件”参数中键入新名称。
1. 在 [!DNL User] 列，并单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   的配置窗口 [!DNL .export] 文件。

1. 单击 **[!UICONTROL Query]**，然后修改 [!DNL .export] 文件，如下表所述：

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对于该参数... </th> 
   <th colname="col2" class="entry"> 提供此信息... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Command（命令） </td> 
   <td colname="col2"> <p>可选。要在创建 Output File（输出文件）后执行的程序。此字段必须引用可执行文件（<span class="filepath">.exe</span> 文件），而不是外壳命令。 </p> <p>注意：如果命令参数中含有空格，区段导出将会失败。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 筛选器 </td> 
   <td colname="col2"> <p>可选。一个命名的过滤器或过滤器表达式。您可以使用过滤器编辑器创建一个命名过滤器，然后在此处键入该过滤器的名称，或者也可以直接键入过滤器表达式。 </p> <p>有关过滤器编辑器的详细信息，请参阅 <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> 过滤器编辑器 </a>. 有关过滤器表达式语法的更多信息，请参阅 <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> 过滤器表达式的语法 </a>. </p> <p>将导出 Level（级别）中与过滤器匹配的元素，但不导出其他元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Level（级别） </td> 
   <td colname="col2"> <p>将导出元素的可计数维度。 </p> <p>示例：“访客”级别为每个访客导出一行数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output File（输出文件） </td> 
   <td colname="col2"> <p>已导出数据的路径和文件名。如果配置文件在Data Workbench服务器群集上运行，则每个Data Workbench服务器都会写入一个包含部分数据的输出文件。 </p> <p>Data Workbench服务器安装目录包含一个Exports目录，您可以在其中保存输出文件。 例如，您可以输入 <span class="filepath">Exports\Visitor Segment.txt</span>，其中 <span class="filepath">Visitor Segment.txt</span> 是包含导出数据的文件的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Format（输出格式） </td> 
   <td colname="col2"> 将导出每个 Level（级别）元素的量度或维度数据。如果输出的是制表符分隔的文件，这些字段应使用制表符字符分隔，并且其格式应以适当的换行字符结尾。有关详细信息，请参阅 <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> 关于输出格式 </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule End Time（计划结束时间） </td> 
   <td colname="col2"> <p>可选。日程安排的结束日期和时间，包括时区。 </p> <p>格式：YYYY-MM-DD hh:mm 时区。 </p> <p>示例：2013-08-01 12:01 EDT。 </p> <p>计划导出将在此时停止；当其定义发生更改时仍会重新生成 Output File（输出文件）。如果不定义 Schedule Every（计划时间间隔），则此字段将没有任何意义。有关时区设置的详细信息，请参阅《数据集配置指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Every（计划时间间隔） </td> 
   <td colname="col2"> 可选。重新生成 Output File（输出文件）的频率。支持的值为小时、日、周和月。当其定义发生更改时仍会重新生成输出文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Start Time（计划开始时间） </td> 
   <td colname="col2"> <p>可选。日程安排的开始日期和时间，包括时区。 </p> <p>格式：YYYY-MM-DD hh:mm 时区。 </p> <p>示例：2013-08-01 12:01 EDT。 </p> <p>计划导出将在此时开始，并且日程安排相对于此时间。如果不定义 <span class="wintitle">Schedule Every</span>（计划时间间隔），则此字段将没有任何意义。有关时区设置的详细信息，请参阅《数据集配置指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time Limit (sec)（时间限制（秒）） </td> 
   <td colname="col2"> 可选。在生成区段导出时，允许经过的最大时间。如果超出指定时间间隔，则会重新开始导出。将此值设置为 0（零）可以删除该限制。默认值为 600 秒。 </td> 
  </tr> 
 </tbody> 
</table>

1. 右键单击 **[!UICONTROL (New)]** ，然后单击 **[!UICONTROL Save]**.
1. 若要使此文件对工作配置文件的所有用户可用，请右键单击所创建文件的复选标记 [!DNL .export] 文件 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >保存 [!DNL .export] 文件到Data Workbench服务器会导致导出立即运行一次，即使将“计划开始时间”设置为将来的日期和时间也是如此。

   以下示例 [!DNL .export] 文件。

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >的 [!DNL Visitor Segment.export] 示例中显示的文件引用了访客区段过滤器。 修改此过滤器的定义将更改导出定义。
