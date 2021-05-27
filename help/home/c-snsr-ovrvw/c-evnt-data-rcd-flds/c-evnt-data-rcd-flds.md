---
description: 日志 (.vsl) 文件包含由传感器从服务器收集并由 Data Workbench Server 用于数据集构建过程的事件数据字段。
title: 事件数据记录字段
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 58%

---

# 事件数据记录字段{#event-data-record-fields}

日志 (.vsl) 文件包含由传感器从服务器收集并由 Data Workbench Server 用于数据集构建过程的事件数据字段。

字段名称通常遵循W3C扩展日志文件格式的命名约定。 许多字段带有前缀，用于指示字段中所含信息的源：

* &quot;cs&quot;表示从客户端到服务器的通信
* “sc”表示从服务器到客户端的通信
* “s”表示来自服务器的信息
* “c”表示来自客户端的信息
* “x”表示由Adobe产品创建的信息
