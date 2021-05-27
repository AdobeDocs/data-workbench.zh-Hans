---
description: 在创建引用查找文件以获取经纬度数据的元素点层时，可通过在查找文件中检索每个元素及其关联的经纬度来获取点的位置。
title: 定义引用查找文件的元素点层
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
exl-id: 2275fa8e-82fe-49e4-ab3e-91ec6ecb6233
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 72%

---

# 定义引用查找文件的元素点层{#define-element-point-layers-referencing-lookup-files}

在创建引用查找文件以获取经纬度数据的元素点层时，可通过在查找文件中检索每个元素及其关联的经纬度来获取点的位置。

>[!NOTE]
>
>您可以使用动态点功能，而不是使用查找文件，该功能将位置的纬度和经度嵌入维度每个元素的名称中。 请参阅[使用动态点定义元素点层](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512)。

若要定义引用查找文件的元素点层，必须创建或已经具有以下信息：

* **或** 文件中定 [!DNL Transformation.cfg file] 义的维 [!DNL transformation dataset include] 度。有关转换配置文件的信息，请参阅《数据集配置指南》**。

* **查找文件**，包含用于绘制每个数据点的数据。此文件必须针对每个数据点至少包含三个数据列：键、经度和纬度。有关查找文件所需格式的详细信息，请参阅[元素点层文件格式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)。

* **层文件**，指定查找文件的位置并标识相关的维度和量度以及查找文件中的键、经度和纬度列名称。有关层文件所需格式的详细信息，请参阅[元素点层文件格式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)。

   >[!NOTE]
   >
   >随[!DNL Geography]配置文件提供的[!DNL Zip Points.layer]文件是一个元素点层，用于标识[!DNL Zipcode.dim]文件、[!DNL Sessions.metric]文件、[!DNL Zip Points.txt]查找文件以及查找文件中键、经度、纬度和名称列的名称。

## 元素点查找文件格式{#section-0bc8c652c1bd40eb84078f2af71a5c06}

元素点层查找文件必须至少包含以下三列：

* **[!DNL Key]列：** 此列应包含常用键数据，这允许Data Workbench服务器将查找文件中的数据与数据集中的数据进行连接。[!DNL key]列必须是查找文件中的第一列。 此列中的每一行都标识维度中的一个元素。

* **[!DNL Longitude]列：** 此列应包含列中每个数据点的经 [!DNL Key] 度。

* **[!DNL Latitude]列：** 此列应包含列中每个数据点的纬 [!DNL Key] 度。

* **[!DNL Name]列（可选）：** 如果要指定要在映射中显示的每个数据点的名称，则可以在查 [!DNL Name] 找文件中包含列。

[!DNL Zip Points.txt] 查找文件中的每一行在第一列中包含邮政编码，随后是经度、纬度和关联的城市名称。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## 元素点层文件格式{#section-52d7e92be8354d979af9e7a2210b76f2}

引用查找文件的每个元素点层[!DNL .layer]文件都必须使用以下模板进行格式化：

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
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
   <td colname="col2"> <p>查找文件中包含常用键数据的列的名称，使Data Workbench服务器能够将查找文件中的数据集成到数据集中。 这必须是查找文件中的第一列。 </p> <p>此列中的每一行都是维度的一个元素。此维度必须在 <span class="filepath">Transformation.cfg</span> 文件或<span class="wintitle">转换数据集包含</span>文件中定义，并在该文件的 Dimension（维度）参数中指定。有关转换配置文件的详细信息，请参阅《数据集配置指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维度 </td> 
   <td colname="col2">所含元素与<span class="wintitle">键</span>列中的数据行对应的维度名称（在转换配置文件中定义）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度 </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">呈现模式 1。点大小在屏幕空间中定义（点相对于计算机屏幕始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。此为默认的呈现模式。 </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">呈现模式 2。点大小在世界空间中定义（点相对于地球始终保持常量大小）。点是使用多边形呈现的，因此点大小没有上限。 </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">呈现模式 3。点大小在屏幕空间中定义。点是使用 OpenGL 平滑点呈现的。 </li> 
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
