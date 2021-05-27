---
description: IPLookup 转换获取 IP 地理位置数据或 IP 地理情报数据（由此类数据的任何供应商提供并被 Adobe 转换为专用格式）并将这些数据转换为可用于分析的地理信息。
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 82%

---

# IPLookup{#iplookup}

IPLookup 转换获取 IP 地理位置数据或 IP 地理情报数据（由此类数据的任何供应商提供并被 Adobe 转换为专用格式）并将这些数据转换为可用于分析的地理信息。

新增> *转换类型*菜单中列出了两个[!DNL IPLookup]转换：

* [!DNL IPLookup] Quova for  [!DNL IP geo-location] data

* [!DNL IPLookup] Digital Envoy for  [!DNL IP geo-intelligence] data

定义[!DNL IPLookup]转换时，请为[!DNL IP geo-location]或[!DNL IP geo-intelligence]数据选择适当的转换。

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 转换的描述性名称。可以在此处输入任何名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 应用此转换的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 文件 </td> 
   <td colname="col2"> 对照文件的路径和名称。相对路径指 Data Workbench Server 的安装目录。此文件通常位于 Data Workbench Server 安装目录的 Lookups 目录中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP Address（IP 地址） </td> 
   <td colname="col2"> 从中读取 IP 地址的字段。 </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Outputs（输出） </td> 
   <td colname="col2"> <p>输出字符串的名称。 </p> <p> <span class="wintitle">IPLookup</span> Quova 和 <span class="wintitle">IPLookup</span> Digital Envoy 转换具有不同的输出参数。请确保为 IP 对照数据使用适当的转换。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

在此示例中，[!DNL IP geo-location]数据（在对照文件[!DNL Quova.bin]中）用于创建列出的输出字段。 输出（AOL、ASN、区域代码，等等）可用于创建对访客流量进行地理分析的维度。

![](assets/cfg_TransformationType_IPLookup.png)
