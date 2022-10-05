---
description: 在数学中，Haversine 公式是一个等式，能给出球形上两点之间的曲线距离（从其经度和纬度确认）。
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 79%

---

# Haversine{#haversine}

{{eol}}

在数学中，Haversine 公式是一个等式，能给出球形上两点之间的曲线距离（从其经度和纬度确认）。

就象公式， [!DNL Haversine] 转换需要两组 [!DNL Latitude] 和 [!DNL Longitude] 设置，用这四个输入来计算两个地点之间地球的真实距离。

通过将“In Kilometers”（以公里为单位）标记从 false 改为 true，可以使用英里或公里来代表距离。

![](assets/cfg_TransformationType_Haversine.png)

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| Latitude 1 Field（纬度 1 字段） | 点 1 的纬度。 |  |
| Latitude 2 Field（纬度 2 字段） | 点 2 的纬度。 |  |
| Longitude 1 Field（经度 1 字段） | 点 1 的经度。 |  |
| Longitude 2 Field（经度 2 字段） | 点 2 的经度。 |  |
| 输出 | 计算后，[!DNL Output]（输出）字段包含维度中指定为元素的点之间的距离。 |  |

例如，如果商店的纬度和经度代码为 Lat1、Lon1，并且使用 IP 查找客户的纬度和经度，则可以确定到客户最常购买商店的距离。

>[!NOTE]
>
>如果要识别其他位置的距离，则每个单独位置必须有其自己的纬度和经度字段集。
