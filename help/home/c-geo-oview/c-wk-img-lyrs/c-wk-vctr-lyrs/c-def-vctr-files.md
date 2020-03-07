---
description: 您可以创建引用一个或多个矢量(.vec)文件的矢量层，该矢量层包含定义要在地球上绘制的矢量的数据。
solution: Analytics
title: 定义引用矢量文件的矢量层
topic: Data workbench
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定义引用矢量文件的矢量层{#defining-vector-layers-referencing-vector-files}

您可以创建引用一个或多个矢量(.vec)文件的矢量层，该矢量层包含定义要在地球上绘制的矢量的数据。

To define a vector layer that references one or more [!DNL .vec]files, you must have the following:

* One or more [!DNL .vec]files that contain the data used to draw the vectors on the globe.

   >[!NOTE]
   >
   >To obtain [!DNL .vec] files to use with your vector layers, contact Adobe.

* A layer file that specifies the location of the [!DNL .vec] files. 有关层文件所需格式的详细信息，请参阅[矢量层文件格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a)。

   >[!NOTE]
   >
   >The [!DNL Boundaries.layer] file, provided with the [!DNL Geography] profile, is a vector layer that references the [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec], and [!DNL mwisland.vec] files.

## 矢量层文件格式 {#section-530d03f41ede4a339aebbb680e15240a}

Each vector layer file referencing [!DNL .vec]files must be formatted using the following template:

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| 参数 | 描述 |
|---|---|
| Vec Files（Vec 文件） | Path(s) to the [!DNL .vec] file(s) containing the vector data. |
| Color（颜色） | RGB 颜色矢量，表达为 (红,绿,蓝)。有关矢量中的每种颜色，您可以输入 0.0 到 1.0 之间的值。例如，(1.0, 0.0, 0.0) 是大红，(0.5, 0.5, 0.5) 是灰色。 |
| Alpha（透明度） | 控制地球上显示的矢量的透明度。范围为 0 到 1，其中 0 表示最透明。 |
| Width（宽度） | 可选。设置数据的宽度（以像素为单位）。建议的范围为 1 到 4。 |
| Error Factor（误差因子） | 控制矢量的绘制精度。值越大，矢量的绘制精度越低，速度越快。默认值为 5。 |

[!DNL Boundaries.layer] 文件按照以下方式设置格式：

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```

