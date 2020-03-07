---
description: 在创建引用制表符分隔值 (.tsv) 文件的矢量层时，可通过从 .tsv 文件中检索绘制说明以及经纬度数据来获取矢量数据。
solution: Analytics
title: 引用制表符分隔值文件的矢量图层
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vector layers referencing tab separated values files{#vector-layers-referencing-tab-separated-values-files}

在创建引用制表符分隔值 (.tsv) 文件的矢量层时，可通过从 .tsv 文件中检索绘制说明以及经纬度数据来获取矢量数据。

To define a vector layer that references a [!DNL .tsv] files, you must have the following:

* **包含[!DNL .tsv]** 用于在地球上绘制矢量（包括经度和纬度数据）的数据的文件。 For more information about the required format of the [!DNL .tsv] file, see [Vector TSV File Format](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **指定文件位置的图层文件**[!DNL .tsv] 。 有关层文件所需格式的详细信息，请参阅[矢量层文件格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)。

## Vector TSV file format {#section-a29012c9ff4444ac8a6d41c68482828e}

The [!DNL .tsv] file must contain the following three tab separated columns:

* **[!DNL Begin]:**此列应指示是否开始新行。 此列中的值可以为 0（不开始新行）或 1（开始新行）。
* **[!DNL Longitude]:**此列应包含经度值。
* **[!DNL Latitude]:**此列应包含纬度值。

>[!NOTE]
>
>将忽略任何其他列。

Following is a sample [!DNL .tsv] file that contains data for a vector layer:

![](assets/tsv_vectorlayer.png)

## Vector layer file format {#section-c430923f341f4c93852e9f24b61e82bf}

Each vector layer file referencing [!DNL .tsv] files must be formatted using the following template:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> TSV Files（TSV 文件） </td> 
   <td colname="col2"> <p>包含矢量数据的 <span class="filepath">.tsv</span> 文件的路径。 </p> <p>示例：<span class="filepath">Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color（颜色） </td> 
   <td colname="col2"> RGB 颜色矢量，表达为 (红,绿,蓝)。有关矢量中的每种颜色，您可以输入 0.0 到 1.0 之间的值。例如，(1.0, 0.0, 0.0) 是大红，(0.5, 0.5, 0.5) 是灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha（透明度） </td> 
   <td colname="col2"> 控制地球上显示的矢量的透明度。范围为 0 到 1，其中 0 表示最透明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Width（宽度） </td> 
   <td colname="col2"> 可选。设置数据的宽度（以像素为单位）。建议的范围为 1 到 4。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error Factor（误差因子） </td> 
   <td colname="col2"> 控制矢量的绘制精度。值越大，矢量的绘制精度越低，速度越快。默认值为 5。 </td> 
  </tr> 
 </tbody> 
</table>

