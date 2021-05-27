---
description: 漏斗可视化包括使用多个维度、原始访客数、每个步骤的访客百分比以及单独的范围构建漏斗的功能。
title: 漏斗功能
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 83%

---

# 漏斗功能{#funnel-features}

漏斗可视化包括使用多个维度、原始访客数、每个步骤的访客百分比以及单独的范围构建漏斗的功能。

下面介绍了漏斗可视化的基本功能。

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> 第一个元素 </td> 
   <td colname="col2"> 流程中的第一个漏斗步骤。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> 第三个元素 </td> 
   <td colname="col2">流程中的第三个漏斗步骤。 <p><p>注意：所选的元素不必来自同一维度。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> 途经百分比 </td> 
   <td colname="col2"> 完成三个范围中显示的定义路径的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> 流失浏览器 </td> 
   <td colname="col2">流失箭头。右键单击并选择<span class="uicontrol">添加路径浏览器</span>，可查看访客遵循了其他哪些路径。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> 流失百分比 </td> 
   <td colname="col2">这些百分比用于描述未完成路径的用户的三个流失范围。 <p>这些百分比以下面三个范围表示： </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" />  从此步骤的前一个步骤流失的百分比。 </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" />  从漏斗中的第一个步骤流失的百分比。 </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" />  基于访客总数的流失百分比。 </p></td> 
  </tr> 
 </tbody> 
</table>

## 漏斗步骤 {#section-96a6732558dd4740b73541844f06d3ef}

漏斗中的圆盘表示导航步骤，圆锥表示从一个步骤途经至下一个步骤，箭头表示流失。单击某个圆锥，可选择途经此点的用户，并将他们包含在当前的工作区过滤器中。单击某个箭头，可选择流失的访客。

>[!NOTE]
>
>漏斗可视化图表限制可应用八个步骤。

## 其他漏斗特性和功能 {#section-22a3582db8114ca8bce77f50bbbf296a}

* **调整漏斗的剪贴和级别**。从“可视化”菜单中选择“漏斗”选项。创建漏斗后，可以右键单击标题，将剪贴和级别调整为系统中的任何可计数量度。

   ![](assets/funnel_path_browser_9.png)

* **拖动更多元素**。使用`<Ctrl>` + `<Alt>`键，将更多元素从Dimension表拖放到漏斗中，以添加更多元素。 您可以同时从Dimension表中拖动多个步骤，方法是选择多个项目（使用`<Ctrl>` +单击），然后使用`<Ctrl>` + `<Alt>`键将它们拖动到漏斗可视化。
* **删除步骤**。右键单击可视化中的步骤并单击&#x200B;**是**，可删除元素。

   ![](assets/funnel_path_browser_4.png)

* **重新排列拖至漏斗的步骤**。只需单击步骤将其选中并拖至其他位置，即可重新排列步骤。
* **打开路径浏览器**。通过[添加路径浏览器](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119)功能，可以查看有关客户在流程中途经或流失位置的更多详细信息。

* **添加更多步骤**。最多可以向每个漏斗可视化中添加八个步骤。
* **更改量度**。可以更改量度，以使这些步骤对每个步骤的访问次数或其他某些量度进行计数。可用的选项因数据集而异。
* **在表格视图中显示**。右键单击标题以显示“漏斗可视化”菜单，然后单击&#x200B;**[!UICONTROL Show Tabular View]**。 在表格视图中，您可以选择&#x200B;**[!UICONTROL Show Graph View]**&#x200B;以返回到漏斗的图形表示形式。 要打开表格视图，请右键单击标题，并从菜单中选择“显示表格视图”。

* **比较序列**。比较两个类似序列的有效方式是并排显示它们各自的视图。另外还可以使用复制功能，并排显示表格视图和图表视图。若要打开复制功能，请右键单击标题，然后从菜单中选择“复制”。
