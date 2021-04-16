---
description: 在创建使用动态点的元素点层时，经纬度数据会嵌入维度的每一个元素中。
title: 定义使用动态点的元素点层
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 95%

---

# 定义使用动态点的元素点层{#defining-element-point-layers-using-dynamic-points}

在创建使用动态点的元素点层时，经纬度数据会嵌入维度的每一个元素中。

若要定义使用动态点的元素点层，必须创建或已经具有以下信息：

* ****&#x200B;维度，在 [!DNL Transformation.cfg] 文件或转换数据集包含文件中定义，其中每个元素都包含字符串“latitude,longitude”或“latitude,longitude,name”。

   有关创建维度的步骤，请参阅《数据集配置指南》**。

* **层文件，用于指定相关维度。**

   有关层文件所需格式的详细信息，请参阅[元素点层文件格式](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)。

>[!NOTE]
>
>使用[!DNL Dynamic Points]时，必须确保层文件中指定的维度基数是合理的。 如果数据集的每一行都有不同的纬度和经度，则该维度会很快填满，并且大部分行都归为“Small Elements”元素。由于“Small Elements”元素没有纬度和经度，因此它不会在地球上显示。

## 元素点层文件格式  {#section-bbcc2baa2f754dba81eba93339a97cbd}

必须使用以下模板格式化使用动态点的每一个元素点层文件：

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 维度 </td> 
   <td colname="col2"> <p>维度的名称（在转化配置文件中定义），它必须包含具有字符串“latitude,longitude”或“latitude,longitude,name”的元素，如以下示例所示： 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181,-77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317,-77.8126,Somewhere </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 指标 </td> 
   <td colname="col2"> 对 Dimension（维度）参数中指定的维度求得的量度名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Points（动态点） </td> 
   <td colname="col2"> 启用动态点。设置为 true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scale（缩放） </td> 
   <td colname="col2"> 可选。用于调整层中点大小的值。默认值为 100。值越大点越大，值越小点越小。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 颜色 </td> 
   <td colname="col2"> 可选。RGB 颜色矢量，表达为 (红,绿,蓝)。有关矢量中的每种颜色，您可以输入 0.0 到 1.0 之间的值。例如，(1.0, 0.0, 0.0) 是大红，(0.5, 0.5, 0.5) 是灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendering Mode（呈现模式） </td> 
   <td colname="col2"> <p>可选。表示要用于层的呈现模式的整数值。以下是三个可用的模式： 
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">呈现模式 1。点大小在屏幕空间中定义（点相对于计算机屏幕始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。此为默认的呈现模式。 </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">呈现模式 2。点大小在世界空间中定义（点相对于地球始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。 </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">呈现模式 3。点大小在屏幕空间中定义。点是使用 OpenGL 平滑点呈现的。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL IP Coordinates.layer] 文件按照以下方式设置格式：

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
