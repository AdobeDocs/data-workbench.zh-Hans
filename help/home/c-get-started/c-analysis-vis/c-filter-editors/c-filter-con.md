---
description: 有关使用过滤条件（包括创建新过滤器和向新过滤器添加条件）的信息。
title: 使用过滤条件
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 81%

---

# 使用过滤条件{#working-with-filter-conditions}

有关使用过滤条件（包括创建新过滤器和向新过滤器添加条件）的信息。

## 创建过滤器 {#section-70ba51ae625e493fa3ca70b93ffba406}

* 右键单击&#x200B;**[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**，在工作区中打开过滤器编辑器。

   -或-

* 如果已打开过滤器编辑器并加载过滤器，请右键单击当前过滤器的名称，然后单击&#x200B;**[!UICONTROL New Blank Filter]**。

## 向新过滤器{#section-50986db80f1148c489630a8a63fe9f28}添加条件

1. 创建新的过滤器。确保“设计过滤器”突出显示（相对于“应用过滤器”），表示您正在“设计过滤器”模式下工作。
1. 在标记为&#x200B;**[!UICONTROL Right-click to build filter]**&#x200B;的区域内右键单击，然后选择以下选项之一：

   * 要创建包含过滤器，请单击&#x200B;**[!UICONTROL Include group with]**。
   * 要创建排除过滤器，请单击&#x200B;**[!UICONTROL Exclude group with]**。

1. 选择要添加到过滤器的条件类型。

   下表提供了对可用过滤条件类型的描述：

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 条件类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>工作区选择 </p> </td> 
   <td colname="col2"> <p>根据工作区中的选择定义过滤条件。仅当工作区中存在一个或多个选择时该选项才可用。 </p> <p>若要查看有关选择的详细信息，请右键单击条件，然后单击<span class="uicontrol">查看详细信息</span>。随即会显示该条件的标注。 </p> <p>如果在工作区中进行另一个选择，则可以将该选择作为第一个选择的子条件。用逻辑 AND 将这些选择组合在一起。因此，条件包括或排除的数据必须满足所有工作区选择。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>至少一个 </p> </td> 
   <td colname="col2">根据所选择的维度中是否至少存在一个元素，定义过滤条件。若要编辑条件，请右键单击该条件，然后单击<span class="uicontrol">将条件更改为</span>。单击可用的维度之一。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>公式 </p> </td> 
   <td colname="col2"> <p>根据您输入的公式定义过滤条件。必须使用正确的语法，过滤器才能工作。 </p> <p> <p>注意：有关定义过滤器的语法的信息，请参阅<a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15">筛选器表达式的语法</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>量度值 </p> </td> 
   <td colname="col2"> <p>根据您指定的量度值定义过滤条件。 </p> <p>若要定义条件，请遵循以下步骤： 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">右键单击 <span class="uicontrol">[选择级别]</span> &gt; <span class="uicontrol">更改级别</span>以从数据集的维度列表中选择级别和量度。 </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">右键单击 <span class="uicontrol">[选择量度]</span> &gt; <span class="uicontrol">更改量度</span>以从数据集的量度列表中选择量度。 </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">右键单击“小于”，然后单击<span class="uicontrol">更改比较</span>以选择可用的比较条件之一（“小于”、“大于”、“精确”、“至少”或“至多”）。 </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">为量度键入所需的值。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>第一个/最后一个 </p> </td> 
   <td colname="col2"> <p>定义一个过滤器，使用该过滤器包括或排除具有指定维度的级别。例如，您可能会指定一个“第一个/最后一个”过滤器来包括（或排除）： </p> <p>最后一次页面查看为 <span class="filepath">/hme/rts/Our Rates</span> 页面的会话。 </p> <p>定义“第一个/最后一个”条件： 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">选择<span class="uicontrol">组包括依据</span>或<span class="uicontrol">组排除依据</span> &gt; <span class="uicontrol">第一个/最后一个</span>作为过滤器编辑器中的新条件。 </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">右键单击 <span class="uicontrol">[选择容器]</span> &gt; <span class="uicontrol">更改容器</span>以选择容器。 </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">右键单击<span class="uicontrol">第一个</span>或<span class="uicontrol">最后一个</span>以指定级别。 </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">右键单击以指定维度，然后在可用的字段中键入值。 </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">单击<span class="uicontrol">应用</span>。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

此示例中的过滤器为最后一页视图为[!DNL /hme/rts/Our Rates]的用户定义第一个/最后一个过滤器：

![](assets/client-fil2.png)

1. （可选）若要向过滤器中添加更多条件，请右键单击在其中构建过滤器的窗口区域，然后选择过滤器类型（请参阅步骤 2）和条件规则（请参阅步骤 3）。

   >[!NOTE]
   >
   >多个包含条件作为逻辑OR组合在一起。 因此，过滤出的包括数据必须至少满足其中一个定义的包括条件。多个排除条件也以逻辑 OR 的形式组合到一起。若要被排除，数据必须至少满足其中一个排除条件。

此示例中的过滤器定义了一个数据子集，该子集包含已给很多影片打分但没有给任何一部影片打高分（4 或 5）的影片观看者（用户）。此过滤器（相应地命名为 Very Hard to Please）包含两个条件：

* **量度值条件：**&#x200B;该条件包括至少对 500 部电影评分的用户。
* **工作区选择条件：**&#x200B;该条件排除对任何一部电影打 4 分或 5 分的用户。标注告诉您 4 分和 5 分是从“得分”维度中选出的元素。

![](assets/vis_FilterEditor_ExampleMovies.png)

## 删除筛选器条件{#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>只有在“设计过滤器”模式下才能删除条件。 如果您已对工作区应用过滤器，则必须单击“设计过滤器”以返回“设计过滤器”模式，然后才能删除一个或多个过滤条件。

* 单击条件左侧的 **x** 即可将其删除。

## 编辑条件说明{#section-5015fd2c88ed4b6a95be7f0d53be2db0}

可以向添加到过滤器的每个条件中添加描述。可以根据需要编辑或删除描述。

>[!NOTE]
>
>仅当您在“设计过滤器”模式下工作时，才显示条件说明。

* 右键单击条件，然后单击&#x200B;**[!UICONTROL Edit description]**。

   * 要添加或编辑说明，请在[!DNL Edit condition description]字段中键入说明。 在过滤器编辑器窗口中，描述显示在条件上面的引号中。

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* 要删除描述，请单击&#x200B;**[!UICONTROL Remove description]**。 该条件仍然位于过滤器编辑器窗口中。
