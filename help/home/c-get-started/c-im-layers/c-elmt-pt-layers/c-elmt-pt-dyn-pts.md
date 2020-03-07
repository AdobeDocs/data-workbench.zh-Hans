---
description: 在创建使用动态点的元素点层时，经纬度数据会嵌入维度的每一个元素中。
solution: Analytics
title: 使用动态点定义元素点层
topic: Data workbench
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Define element point layers using dynamic points{#define-element-point-layers-using-dynamic-points}

在创建使用动态点的元素点层时，经纬度数据会嵌入维度的每一个元素中。

若要定义使用动态点的元素点层，必须创建或已经具有以下信息：

* A dimension, defined in the [!DNL Transformation.cfg] file or a [!DNL transformation dataset include] file, in which each element contains the string “latitude,longitude” or “latitude,longitude,name.”

   有关创建维度的步骤，请参阅《数据集配置指南》**。

* 层文件，用于指定相关维度。

有关层文件所需格式的详细信息，请参阅[元素点层文件格式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0)。

>[!NOTE]
>
>When using [!DNL Dynamic Points], it is essential to ensure that the cardinality of the dimension specified in the layer file is reasonable. 如果数据集的每一行都有不同的纬度和经度，则该维度会很快填满，并且大部分行都归为“Small Elements”元素。由于“Small Elements”元素没有纬度和经度，因此它不会在地球上显示。

## Element point layer file format {#section-0645fbc761c14bb986f3d6f02df407a0}

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

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimension（维度） </td> 
   <td colname="col2"> <p>维度的名称（在转化配置文件中定义），它必须包含具有字符串“latitude,longitude”或“latitude,longitude,name”的元素，如以下示例所示： 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126,Somewhere </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metric（量度） </td> 
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
   <td colname="col1"> Color（颜色） </td> 
   <td colname="col2"> 可选。RGB 颜色矢量，表达为 (红,绿,蓝)。有关矢量中的每种颜色，您可以输入 0.0 到 1.0 之间的值。例如，(1.0, 0.0, 0.0) 是大红，(0.5, 0.5, 0.5) 是灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendering Mode（呈现模式） </td> 
   <td colname="col2"> <p>可选。表示要用于层的呈现模式的整数值。以下是三个可用的模式： 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">呈现模式 1。点大小在屏幕空间中定义（点相对于计算机屏幕始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。此为默认的呈现模式。 </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">呈现模式 2。点大小在世界空间中定义（点相对于地球始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。 </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">呈现模式 3。点大小在屏幕空间中定义。点是使用 OpenGL 平滑点呈现的。 </li> 
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

