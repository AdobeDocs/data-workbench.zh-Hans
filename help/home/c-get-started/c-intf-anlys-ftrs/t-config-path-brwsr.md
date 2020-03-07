---
description: 可以将路径浏览器配置为使用基本维度、组维度、级别维度和对应用程序和数据集有益的量度的组合。
solution: Analytics
title: 配置路径浏览器
topic: Data workbench
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置路径浏览器{#configure-a-path-browser}

可以将路径浏览器配置为使用基本维度、组维度、级别维度和对应用程序和数据集有益的量度的组合。

After you configure a path browser, it is listed with other path browsers in the [!DNL Add Visualization] menu.

1. 在中，单 [!DNL Profile Manager]击，然 **[!UICONTROL Menu]**&#x200B;后单击 **[!UICONTROL Add Visualization]** 并单击 **[!UICONTROL Path Browser]**。

   At least one [!DNL *.vw] file resides in the Path Browser directory.

1. Right-click the check mark for the desired file and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 参考以下示例文件和表格，编辑文件的参数：

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对于该参数... </th> 
   <th colname="col2" class="entry"> 提供此信息... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Base dimension name（基本维度名称）</i> </p> </td> 
   <td colname="col2"> <p>元素显示在路径浏览器上的维度的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Group dimension name（组维度名称）</i> </p> </td> 
   <td colname="col2"> <p>维度的名称，此维度用于确定如何组合级别维度的元素以形成路径浏览器中的路径。具体来说，与路径浏览器中单个路径相关联的级别维度元素不能跨越组维度的多个元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level dimension name（级别维度名称）</i> </p> </td> 
   <td colname="col2"> <p>将其元素拖动到路径浏览器的基本维度的级别（父级）名称。当您沿一条路径从一个基本维度元素到下一个基本维度元素时，便从一个级别维度元素移动到下一个级别维度元素。当您选择基本维度元素的某个路径时，即选择了对应级别维度元素的数据。该选择始终包括与根相关的级别维度的元素，并且可以通过向路径添加其他元素加以完善。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metric name（量度名称）</i> </p> </td> 
   <td colname="col2"> <p>量度的名称，该量度的指定元素值与到该元素的路径的深度成正比。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>For more information about the base dimension, group dimension, level dimension, and metric for a path browser, see [Path Browsers](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the file with a new name based on the group dimension, that is, *Group dimension name*.vw.

   确保您将文件保存到路径浏览器目录中。

   >[!NOTE]
   >
   >To make sure that your path browser is saved as a [!DNL *.vw] file, in the [!DNL Save As] window, set Save as type to All Files.

1. (Optional) To make the changes available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
