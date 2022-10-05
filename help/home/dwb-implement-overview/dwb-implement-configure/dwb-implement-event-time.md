---
description: 本节介绍如何为Data Workbench数据集创建时间戳。
title: 设置事件时间
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
exl-id: 9632e713-5cf9-4acf-aafa-bfdf79a51ad9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 11%

---

# 设置事件时间{#setting-up-event-time}

{{eol}}

本节介绍如何为Data Workbench数据集创建时间戳。

## 了解事件时间 {#section-e10ef2b5b6244dc5b215836e3c77d663}

Event Time（事件时间）是发生请求（或事件）的日期和时间。

通常，对于在线数据， *x_hit_time_gmt* 用作时间戳字段。 调用的时间可用作离线数据（如呼叫中心数据）的时间戳。 这是必填字段，所有数据源中应有一个可用作时间戳的字段。 此信息应由贵组织提供。

在DWB中，以下预定义变量会捕获时间戳：

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> 服务器接收到请求的日期和时间 (GMT)。该时间以从 1600 年 1 月 1 日算起的总时间数表示（以 100 纳秒为单位）。 </p> <p>示例：127710989320000000是 <i>x-timestamp</i> 值11:28:52.0000000 2005年9月13日星期二。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> 格式为YYYY-MM-DD HH:MM:SS，嗯。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> 是表示自1970年1月1日(00)起的秒数的epoc时间:00:01. </td> 
  </tr> 
 </tbody> 
</table>

根据日期字段的格式，使用x-timestamp或x-unixtime或x-timestring。 例如，如果传入数据的格式为YYYY-MM-DD，则将使用x-timestring。

时间戳以一种格式定义，DWB会内部生成其他两种格式。 此外，这些是预定义的DWB字段，不应将同一名称用于任何其他字段。

## DWB中定义的时区 {#section-3cdd12254342442b917376661e1d9c9f}

如果日期字段包含以下任何时区，DWB会考虑该特定时区中的整行。 例如，一个文件的日期定义为2015-01-01 00:00:00 gmtand另一个文件的值为2015-01-01 00:00:00cst时，则第一个文件的日期将被视为GMT时区，而第二个文件的日期将被视为CST时区。

| 代码 | 时区 |
|---|---|
| gmt | 格林威治标准时间 |
| est | 东部标准时间 |
| edt | 东部夏令时 |
| cst | 中部标准时间 |
| cdt | 中部夏令时 |
| mst | 山地标准时间 |
| mdt | 山地夏令时 |
| pst | 太平洋标准时间 |
| pdt | 太平洋夏令时 |

>[!NOTE]
>
>DWB仅处理上述时区。

## 设置自定义时区 {#section-7c351921f22b439b81c73f40d5b47536}

DWB不处理时区中的偏移。 要考虑时区中的偏移，数据应在该偏移时区中进行格式化。

示例：要考虑CST时区中的日期格式，数据应采用YYYY-MM-DD HH格式:MM:客户端中的SS UTC +/-HHMM格式。

2015-10-18 05:00:世界协调时–200

## 如何设置事件时间/时间戳 {#section-81507080f0b44ae6b83d3650ba019812}

根据日期字段格式， *x-timestamp、x-unixtime* 或 *x-timestring* 变量。 在以下示例中，由于 *x_hit_time_gmt* 是unix epo格式， *x-unixtime* 中，将使用。

在DWB中 [!DNL foundation.cfg] 文件（或数据集日志处理文件夹下的任何其他配置文件）中，使用复制转换设置事件时间，如下所示：

根据日期字段格式，使用x-timestamp、x-unixtime或x-timestring变量。 在以下示例中，由于x-hit_time_gmt采用unix epoc格式，因此使用x-unixtime。

在insight foundation.cfg（或Datasetà日志处理文件夹下的任何其他配置）中，使用Copy转换设置事件时间，如下所示： ![](assets/dwb_impl_timestamp1.png)

如果的日期为YYYY-MM-DD HH:MM:SS.mmm格式，使用x-timestring。 ![](assets/dwb_impl_timestamp2.png)示例：如果日期字段的格式不同于在DWB（如YYYY/MM/DD）中定义的格式，则首先将其格式化为DWB接受的时间戳格式之一，然后将其分配给相应的变量。 在以下屏幕截图中，日期首先转换为YYYY-MM-DD格式，然后分配给*x-timestring *variable。 ![](assets/dwb_impl_timestamp3.png)
