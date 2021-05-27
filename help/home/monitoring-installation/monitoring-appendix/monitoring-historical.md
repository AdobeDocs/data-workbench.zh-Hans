---
description: 以下维度可在Data Workbench历史配置文件中使用。
title: Data Workbench 历史配置文件中的维度
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Data Workbench 历史配置文件中的维度{#dimensions-in-the-data-workbench-historic-profile}

以下维度可在Data Workbench历史配置文件中使用。

## Data Workbench 历史配置文件中的维度 {#section-96f1b64f5cb84411b630f97f227d888d}

以下维度可在Data Workbench历史配置文件中使用。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>块</b> </td> 
   <td colname="col2">这是此配置中唯一可计数的，它是所有维的根。 块可以被视为服务器。 它使用的是x-trackingid字段。 <p>注意： 块ID是服务器名称加主机名的哈希，因此每个配置文件的每个服务器大约会有一个块。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> 这是基于块可计数的可计数维度。 配置文件中的每一行数据都是来自监视代理的ping。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>严重警报</b> </td> 
   <td colname="col2"> 从cs-uri-query(ad)值构建的数值Dimension。 它在Ping级别构建，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警报关闭</b> </td> 
   <td colname="col2"> 从cs-uri-query(ac)值构建的数值Dimension。 它在Ping级别构建，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警报警告</b> </td> 
   <td colname="col2"> 从cs-uri-query(ae)值构建的数值Dimension。 它在Ping级别构建，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>重新处理任何配置文件</b> </td> 
   <td colname="col2"> 从cs-uri-query(aa)值构建的数值Dimension。 该函数在Ping级别构建，条件是cs-uri-query(a)与“1”匹配，且cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟分钟数</b> </td> 
   <td colname="col2"> cs-uri-query(bi)会放入x-as-of-delay-minutes字段中，并四舍五入到最接近的分钟数。 它在Ping级别构建，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>能力行百分比</b> </td> 
   <td colname="col2"> 从cs-uri-query(r)值构建的数字Dimension。 该函数在Ping级别构建，条件是cs-uri-query(a)与“1”匹配，且cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> 从cs-uri-query(n)值构建的数字Dimension。 该函数在Ping级别构建，条件是cs-uri-query(a)与“1”匹配，且cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查成功</b> </td> 
   <td colname="col2"> 从cs-uri-query(v)值构建的简单Dimension。 它在Ping级别构建，并且条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出错的组件</b> </td> 
   <td colname="col2"> cs-uri-query(ao)由“|”分隔符拆分，并复制到x-components-in-error字段中。 从“错误中的x组件”字段构建的“多对多”Dimension。 在Ping级别构建。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>详细检查秒数</b> </td> 
   <td colname="col2"> 从cs-uri-query(l)值构建的数字Dimension。 它在Ping级别构建，条件是cs-uri-query(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>详细检查成功</b> </td> 
   <td colname="col2"> 从cs-uri-query(k)值构建的简单Dimension。 它在Ping级别构建，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DimensionGigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc)将复制到x-dimension-gbs字段中。 x-dimension-gbs字段是此简单Dimension的用户，条件为cs-uri-query(a)匹配“2”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁盘“x”已用百分比</b> </td> 
   <td colname="col2"> 这些数值Dimension是使用cs-uri-query(ah， ai， aj， ak， al)值配置的。 它们在Ping级别构建，并且以cs-uri-query(a)与“1”匹配为条件，且cs-uri-query(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描秒数</b> </td> 
   <td colname="col2"> 此数值Dimension中使用x-estimated-sweep-dekaseconds字段。 这是服务器的估计扫描时间除以10（降低扫描测量分辨率以使维度更合理地大小）。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入MegaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值将用于此维度。 块的“最后一行”将用作维度的值。 如果Dimension集在“快速输入”中，则此数值数据的值将显示系统输入数据的每分钟MB。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并MegaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用于此维度。 块的最后一行将用作维度的值。 如果Dimension集处于“快速合并”中此数值数据的值将显示系统合并时每分钟的MB。 <p><p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bg)值用于此维度。 该值除以1000，然后四舍五入到最接近的整数。 此数值Dimension的值将显示数据集中的字段正在使用的空间量。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 从cs-uri-query(x)值在Ping级别构建的简单Dimension。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主机</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用于此维度。 简单维度的值是块的最后一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2"> x-unixtime字段将复制为x-last-ping并除以10以减少基数。 数值Dimension在块级别构建，并使用x-last-ping字段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>加载平均值</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-query(i)值的最后一行的数字维度。 它以cs-uri-query(k)不为空为条件。 此维度用于计算所监视系统中服务器的平均负载。 <p><p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志读取百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值用于在Ping级别构建的此数值维度。 此维度用于计算读取的日志百分比。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件百分比</b> </td> 
   <td colname="col2"> 这是使用cs-uri-query(o)值的数字维度，在Ping级别构建。 它以cs-uri-query(k)不为空和cs-uri-query(a)匹配“1”为条件。 此维度用于计算页面文件内存使用率的百分比。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理兆字节总数</b> </td> 
   <td colname="col2">这是使用cs-uri-query(ag)值的数值维度，在Ping级别构建。 它以cs-uri-query(k)不为空和cs-uri-query(a)匹配“1”为条件。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理百分比</b> </td> 
   <td colname="col2">这是使用cs-uri-query(ag)值的数值维度，在Ping级别构建。 它以cs-uri-query(k)不为空和cs-uri-query(a)匹配“1”为条件。 此维度用于计算每个服务器的物理内存使用率百分比。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询百分比</b> </td> 
   <td colname="col2"> 这是在Ping级别使用cs-uri-query值的数值维度。 它以cs-uri-query(k)不为空和cs-uri-query(a)匹配“1”为条件。 此维度用于计算每个服务器的查询内存使用率百分比。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是使用在Ping级别构建的cs-uri-query(q)值的数值维度。 它以cs-uri-query(k)不为空和cs-uri-query(a)匹配“1”为条件。 用于显示给定服务器的网络连接数。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>输出行</b> </td> 
   <td colname="col2"> cs-uri-query(bh)值除以100000，并复制到x-output-rows字段中，以减小维度的大小。 X-output-rows用在在Ping级别构建的数字Dimension中，条件是cs-uri-query(a)与“2”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping类型ID</b> </td> 
   <td colname="col2"> 在Ping级别使用cs-uri-query(a)值构建的简单Dimension。 这显示了Ping的录制类型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轮询延迟厘秒</b> </td> 
   <td colname="col2">cs-uri-query(m)值除以10可减小维度大小，并复制到x-poll-latency-entiseconds字段中。 这是在Ping级别构建的数值维度，条件是cs-uri-query(k)不为空，且cs-uri-query(a)与“1”/匹配。此维度用于计算轮询延迟。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用于在Ping级别构建的此简单Dimension。 它的条件是cs-uri-query(bb)不为空，并且cs-uri-query(a)与“2”处理模式ID匹配，使用户能够查看系统处理模式（快速输入、快速合并、实时）。 <p>注意： 此维度会被隐藏，然后在客户端维度处理模式中使用友好值重新显示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>用户档案</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用于此简单Dimension，它在Ping级别构建。 此维度显示当前正在监控的配置文件的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查秒数</b> </td> 
   <td colname="col2"> cs-uri-query(h)值用于此数值Dimension。 它在Ping级别构建，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查成功</b> </td> 
   <td colname="col2"> 这是一个基于在Ping级别构建的cs-uri-query(g)值构建的简单维度。 它用于计算快速检查量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>实时处理百分比</b> </td> 
   <td colname="col2"> 使用在Ping级别构建的cs-uri-query(t)值进行数值Dimension。 条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后源</b> </td> 
   <td colname="col2"> 从Ping级别生成的cs-uri-query(bl)值构建的简单Dimension。 此维度显示上次与数据源联系的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库空间百分比</b> </td> 
   <td colname="col2">使用cs-uri-query(an)值构建的数值Dimension，在Ping级别构建。 它的条件是cs-uri-query(k)不为空，且cs-uri-query(a)与“1”匹配。 它用于计算给定服务器上已用临时数据库空间的百分比。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换百分比</b> </td> 
   <td colname="col2">cs-uri-query(bf)值用于此数值维度。 它是在Ping级别构建的。 此维度用于计算完成数据转换的百分比。 <p><p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版本</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用于此简单Dimension。 它在Ping级别构建，并且条件是cs-uri-query(ab)不为空，且cs-uri-query(a)与“1”匹配。 这会显示每个服务器上运行的Data Workbench Server的版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版本主要</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值被拆分，主发行值将复制到x-insight-version-major字段中。 它是在Ping级别构建的简单Dimension，并且条件是x-insight-version-major不为空，且cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
