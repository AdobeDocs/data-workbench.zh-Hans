---
description: 传感器内容类型过滤功能的目的是消除存储和处理用于分析目的不有用的信息的需要。
title: 按内容类型过滤
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# 按内容类型过滤{#filtering-by-content-type}

传感器内容类型过滤功能的目的是消除存储和处理用于分析目的不有用的信息的需要。

通过Web服务器的API提供的许多请求数据在业务分析中没有用处。 存储和处理成本高昂，而[!DNL Sensor’s]内容类型过滤使您能够避免不必要的存储和处理。

为了最大化网络日志数据处理性能并减少必须存储的测量数据量，[!DNL Site]为所有Web内容类型请求获取测量数据（请求数据、日志条目、日志数据等），但具体列出的内容类型（如级联样式表、图像请求等）除外，这些内容类型在通过[!DNL Sensor]将它们传输到Data Workbench Server之前会被过滤掉。 此过滤功能对于整个Web服务器而言是禁用的，并且还可以通过将名称 — 值对&quot;Log=1&quot;添加到特定嵌入对象的查询字符串（例如[!DNL https://www.mysite.com/advertisement.gif?Log=1]）来覆盖特定内容对象的此过滤功能。
