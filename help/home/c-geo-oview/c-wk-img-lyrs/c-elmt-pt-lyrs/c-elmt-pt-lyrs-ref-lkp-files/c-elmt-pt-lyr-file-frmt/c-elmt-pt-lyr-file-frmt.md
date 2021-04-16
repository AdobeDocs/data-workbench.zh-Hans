---
description: 设置有关元素点图层文件的格式信息。
title: 元素点层文件格式
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 92%

---

# 元素点层文件格式{#element-point-layer-file-format}

设置有关元素点图层文件的格式信息。

引用查找文件的每个元素点层[!DNL .layer]文件必须使用以下模板进行格式化：

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Data Paths（数据路径） </td> 
   <td colname="col2"> 包含经纬度数据的查找文件的路径。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitude Column（经度列） </td> 
   <td colname="col2"> 查找文件中包含经度数据的列名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude Column（纬度列） </td> 
   <td colname="col2"> 查找文件中包含纬度数据的列名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name Column（名称列） </td> 
   <td colname="col2"> 可选。查找文件中包含由经纬度数据表示的位置名称的列名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Key Column（键列） </td> 
   <td colname="col2"> <p>查找文件中包含常用键数据的列名称，这允许 Data Workbench Server 将查找文件中的数据集成到数据集中。这必须是查找文件中的第一列。 </p> <p>此列中的每一行都是维度的一个元素。此维度必须在 <span class="filepath">Transformation.cfg</span> 文件或转换数据集包含文件中定义，并在该文件的 Dimension（维度）参数中指定。有关转换配置文件的详细信息，请参阅《数据集配置指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维度 </td> 
   <td colname="col2">所含元素与<span class="wintitle">键</span>列中的数据行对应的维度名称（在转换配置文件中定义）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 指标 </td> 
   <td colname="col2"> 对 Dimension（维度）参数中指定的维度求得的量度名称。 </td> 
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
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">呈现模式 1。点大小在屏幕空间中定义（点相对于计算机屏幕始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。此为默认的呈现模式。 </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">呈现模式 2。点大小在世界空间中定义（点相对于地球始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。 </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">呈现模式 3。点大小在屏幕空间中定义。点是使用 OpenGL 平滑点呈现的。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Zip Points.layer] 文件按照以下方式设置格式：

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
