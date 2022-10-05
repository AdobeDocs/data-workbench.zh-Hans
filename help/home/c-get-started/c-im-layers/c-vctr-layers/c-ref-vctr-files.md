---
description: 您可以创建引用一个或多个矢量 (.vec) 文件的矢量层，文件中包含定义要在地球上绘制的矢量的数据。
title: 定义引用矢量文件的矢量图层
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 66%

---

# 定义引用矢量文件的矢量图层{#define-vector-layers-referencing-vector-files}

{{eol}}

您可以创建引用一个或多个矢量 (.vec) 文件的矢量层，文件中包含定义要在地球上绘制的矢量的数据。

定义引用一个或多个的矢量层 [!DNL .vec] 文件，则必须具有以下内容：

* **一个或多个 [!DNL .vec] 文件** 包含用于在地球上绘制矢量的数据。

   >[!NOTE]
   >
   >获取 [!DNL .vec] 要与矢量层一起使用的文件，请联系Adobe。

* **层文件** 指定 [!DNL .vec] 文件。 有关层文件所需格式的详细信息，请参阅[矢量层文件格式](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1)。

   >[!NOTE]
   >
   >的 [!DNL Boundaries.layer] 文件，随 [!DNL Geography] 配置文件是引用的矢量层 [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]和 [!DNL mwisland.vec] 文件。

## 矢量层文件格式 {#section-83a0077cf0c8479b9e7b2939bc761af1}

引用的每个矢量层文件 [!DNL .vec] 文件必须使用以下模板进行格式设置：

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
| Vec Files（Vec 文件） | 路径 [!DNL .vec] 包含矢量数据的文件。 |
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
