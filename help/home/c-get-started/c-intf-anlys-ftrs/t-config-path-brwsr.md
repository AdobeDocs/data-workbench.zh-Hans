---
description: 可以将路径浏览器配置为使用基本维度、组维度、级别维度和对应用程序和数据集有益的量度的组合。
title: 配置路径浏览器
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 65%

---

# 配置路径浏览器{#configure-a-path-browser}

可以将路径浏览器配置为使用基本维度、组维度、级别维度和对应用程序和数据集有益的量度的组合。

配置路径浏览器后，它会与[!DNL Add Visualization]菜单中的其他路径浏览器一起列出。

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Menu]**，然后单击&#x200B;**[!UICONTROL Add Visualization]**&#x200B;和&#x200B;**[!UICONTROL Path Browser]**。

   路径浏览器目录中至少有一个[!DNL *.vw]文件。

1. 右键单击所需文件的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。
1. 右键单击[!DNL User]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
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
>有关路径浏览器的基本维度、组维度、级别维度和量度的详细信息，请参阅[路径浏览器](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b)。

1. 在记事本中，单击&#x200B;**[!UICONTROL File]** > **[!UICONTROL Save As]**&#x200B;以根据组维度（即&#x200B;*组维度名称*.vw）使用新名称保存文件。

   确保您将文件保存到路径浏览器目录中。

   >[!NOTE]
   >
   >要确保路径浏览器保存为[!DNL *.vw]文件，请在[!DNL Save As]窗口中将“另存为类型”设置为“所有文件”。

1. （可选）要使更改对工作用户档案的所有用户可用，请在[!DNL Profile Manager]中右键单击[!DNL User]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。
