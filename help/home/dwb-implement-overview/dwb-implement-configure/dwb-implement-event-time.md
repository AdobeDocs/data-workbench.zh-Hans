---
description: 本节介绍如何为Data Workbench数据集创建时间戳。
title: 设置活动时间
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 设置活动时间{#setting-up-event-time}

本节介绍如何为Data Workbench数据集创建时间戳。

## 了解活动时间 {#section-e10ef2b5b6244dc5b215836e3c77d663}

事件时间是发生请求（或事件）的日期和时间。

通常，对于联机数据， *x_hit_time_gmt* 用作时间戳字段。 呼叫时间可用作离线数据（如呼叫中心数据）的时间戳。 这是必填字段，所有数据源中应包含一个可用作时间戳的字段。 此信息应由您的组织提供。

在DWB中，以下预定义变量捕获时间戳：

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> 服务器接收到请求的日期和时间 (GMT)。该时间以从 1600 年 1 月 1 日算起的总时间数表示（以 100 纳秒为单位）。 </p> <p>Example: 127710989320000000 would be the <i>x-timestamp</i> value for 11:28:52.0000000 on Tuesday,September 13, 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>YYYY-MM-DD HH:MM:SS.mmm 格式的 x-timestamp。</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> 是表示自1970年1月1日00:00:01以来的秒数的epoc时间。 </td> 
  </tr> 
 </tbody> 
</table>

根据日期字段的格式，使用x-timestamp或x-unixtime或x-timestring。 例如，如果传入数据的格式为YYYY-MM-DD，则使用x-timestring。

时间戳以一种格式定义，DWB内部生成另外两种格式。 此外，这些是预定义的DWB字段，同名不应用于任何其他字段。

## DWB中定义的时区 {#section-3cdd12254342442b917376661e1d9c9f}

如果日期字段包含以下任一时区，则DWB会考虑该特定时区中的整行。 例如，一个文件的日期定义为2015-01-01 00:00:00 gmt，另一个文件的值为2015-01-01 00:00:00 cst，则第一个文件的日期将在GMT时区中考虑，而第二个文件的日期将在GMT时区CST时区。

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

DWB不处理时区中的偏移。 要考虑时区中的偏移，应在该偏移时区中设置数据格式。

示例：要考虑CST时区中的日期格式，数据应以客户端的YYYY-MM-DD HH:MM:SS UTC +/-HHMM格式提供。

世界协调时2015-10-18 05:00:00

## 如何设置活动时间／时间戳 {#section-81507080f0b44ae6b83d3650ba019812}

根据日期字段格式， *使用x-timestamp、x-unixtime**或x-timestring* 变量。 在以下示例中，由于 *x-hit_time_gmt采用unix epoc格式* ，因此使用 *x-unixtime* 。

在DWB文件( [!DNL foundation.cfg] 或数据集日志处理文件夹下的任何其他配置文件)中，使用“复制”转换设置“事件时间”，如下所示：

根据日期字段格式，使用x-timestamp、x-unixtime或x-timestring变量。 在以下示例中，由于x-hit_time_gmt采用unix epoc格式，因此使用x-unixtime。

在insight foundation.cfg（或Datasetà日志处理文件夹下的任何其他配置）中，使用Copy转换设置事件时间，如下所示： ![](assets/dwb_impl_timestamp1.png)

如果日期为YYYY-MM-DD HH:MM:SS.mmm格式，则使用x-timestring。 ![](assets/dwb_impl_timestamp2.png)示例：如果日期字段的格式不同于在DWB中定义的YYYY/MM/DD格式，则首先将其格式化为DWB接受的时间戳格式之一，然后将其分配给相应的变量。 在以下屏幕截图中，日期首先转换为YYYY-MM-DD格式，然后被分配给*x-timestring *variable。 ![](assets/dwb_impl_timestamp3.png)

