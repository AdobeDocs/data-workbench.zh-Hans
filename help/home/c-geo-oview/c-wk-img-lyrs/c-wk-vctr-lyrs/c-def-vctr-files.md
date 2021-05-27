---
description: 您可以创建引用一个或多个矢量(.vec)文件的矢量层，其中包含定义要在地球上绘制的矢量的数据。
title: 定义引用矢量文件的矢量图层
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 47%

---

# 定义引用矢量文件的矢量图层{#defining-vector-layers-referencing-vector-files}

您可以创建引用一个或多个矢量(.vec)文件的矢量层，其中包含定义要在地球上绘制的矢量的数据。

要定义引用一个或多个[!DNL .vec]文件的矢量层，必须具有以下内容：

* 一个或多个[!DNL .vec]文件，其中包含用于在地球上绘制矢量的数据。

   >[!NOTE]
   >
   >要获取要与矢量层一起使用的[!DNL .vec]文件，请联系Adobe。

* 指定[!DNL .vec]文件位置的层文件。 有关层文件所需格式的详细信息，请参阅[矢量层文件格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a)。

   >[!NOTE]
   >
   >随[!DNL Geography]配置文件提供的[!DNL Boundaries.layer]文件是引用[!DNL mwnation.vec]、[!DNL mwstate.vec]、[!DNL mwcoast.vec]、[!DNL mwlake.vec]和[!DNL mwisland.vec]文件的矢量层。

## 矢量层文件格式 {#section-530d03f41ede4a339aebbb680e15240a}

引用[!DNL .vec]文件的每个矢量层文件都必须使用以下模板进行格式化：

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
| Vec Files（Vec 文件） | 包含矢量数据的[!DNL .vec]文件的路径。 |
| 颜色 | RGB 颜色矢量，表达为 (红,绿,蓝)。有关矢量中的每种颜色，您可以输入 0.0 到 1.0 之间的值。例如，(1.0, 0.0, 0.0) 是大红，(0.5, 0.5, 0.5) 是灰色。 |
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
