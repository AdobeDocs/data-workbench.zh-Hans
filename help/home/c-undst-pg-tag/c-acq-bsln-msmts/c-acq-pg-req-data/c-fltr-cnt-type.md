---
description: 传感器的内容类型过滤功能旨在消除存储和处理用于分析目的不有用的信息的需求。
solution: Analytics
title: 按内容类型筛选
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 按内容类型筛选{#filtering-by-content-type}

传感器的内容类型过滤功能旨在消除存储和处理用于分析目的不有用的信息的需求。

通过Web服务器的API可用的许多请求数据在业务分析中不有用。 存储和处理费用高昂，而 [!DNL Sensor’s] 内容类型过滤使您能够避免不必要的存储和处理。

为了最大化Web日志数据处理性能并减少必须存储的测量数据量， [!DNL Site] 为所有Web内容类型请求获取测量数据（请求数据、日志条目、日志数据等），除特别列出的内容类型（如级联样式表、图像请求等）外，这些数据在被传输到Data Workbench Server之前被过滤掉 [!DNL Sensor]。 可以对整个Web服务器禁用此过滤功能，并且还可以通过将名称——值对“Log=1”添加到特定嵌入对象的查询字符串(例如， [!DNL http://www.mysite.com/advertisement.gif?Log=1])来覆盖特定内容对象的过滤功能。
