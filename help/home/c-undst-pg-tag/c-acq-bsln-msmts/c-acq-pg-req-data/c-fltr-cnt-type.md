---
description: 传感器的内容类型过滤功能旨在消除存储和处理对分析无用的信息的需求。
title: 按内容类型过滤
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# 按内容类型过滤{#filtering-by-content-type}

传感器的内容类型过滤功能旨在消除存储和处理对分析无用的信息的需求。

通过Web服务器的API可用的大部分请求数据在业务分析中没有用处。 存储和处理成本高昂，而[!DNL Sensor’s]内容类型过滤使您能避免不必要的存储和处理。

为了最大限度地提高Web日志数据处理性能并减少必须存储的测量数据量，[!DNL Site]获取所有Web内容类型请求的测量数据（请求数据、日志条目、日志数据等），但具体列出的内容类型（如级联样式表、图像请求等）除外，这些类型在通过[!DNL Sensor]发送到Data Workbench Server之前被过滤掉。 可以对整个Web服务器禁用此过滤，还可以通过将名称 — 值对&quot;Log=1&quot;添加到特定嵌入对象的查询字符串（例如[!DNL http://www.mysite.com/advertisement.gif?Log=1]）来覆盖特定内容对象的此过滤。
