---
description: 在数学中，Haversine 公式是一个等式，能给出球形上两点之间的曲线距离（从其经度和纬度确认）。
solution: Analytics
title: Haversine
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversine{#haversine}

在数学中，Haversine 公式是一个等式，能给出球形上两点之间的曲线距离（从其经度和纬度确认）。

Like the formula, the [!DNL Haversine] transform requires two sets of [!DNL Latitude] and [!DNL Longitude] settings, using these four inputs to calculate the true distance across the Earth between two locations.

通过将“In Kilometers”（以公里为单位）标记从 false 改为 true，可以使用英里或公里来代表距离。

![](assets/cfg_TransformationType_Haversine.png)

| 参数 | 描述 | 默认值 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Comments（备注） | 可选。有关转换的说明。 |  |
| Condition（条件） | 应用此转换的条件。 |  |
| Latitude 1 Field（纬度 1 字段） | 点 1 的纬度。 |  |
| Latitude 2 Field（纬度 2 字段） | 点 2 的纬度。 |  |
| Longitude 1 Field（经度 1 字段） | 点 1 的经度。 |  |
| Longitude 2 Field（经度 2 字段） | 点 2 的经度。 |  |
| Output（输出） | 计算后，[!DNL Output]（输出）字段包含维度中指定为元素的点之间的距离。 |  |

例如，如果商店的纬度和经度代码为 Lat1、Lon1，并且使用 IP 查找客户的纬度和经度，则可以确定到客户最常购买商店的距离。

>[!NOTE]
>
>如果要确定其他位置的距离，则每个单独的位置必须有自己的纬度和长度字段集。

