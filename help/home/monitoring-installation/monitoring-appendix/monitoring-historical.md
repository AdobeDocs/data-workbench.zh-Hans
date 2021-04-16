---
description: 以下维可用于Data Workbench历史用户档案。
title: Data Workbench 历史配置文件中的维度
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Data Workbench 历史配置文件中的维度{#dimensions-in-the-data-workbench-historic-profile}

以下维可用于Data Workbench历史用户档案。

## Data Workbench 历史配置文件中的维度 {#section-96f1b64f5cb84411b630f97f227d888d}

以下维可用于Data Workbench历史用户档案。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>阻止</b> </td> 
   <td colname="col2">这是此配置中唯一可计数的，它是所有维的根。 块可以视为服务器。 它使用x-trackingid字段。 <p>注意： 块ID是服务器名称加主机名的哈希值，因此每个用户档案每个服务器大约有一个块。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> 这是由块可数构成的可数维。 用户档案中的每一行数据都是监视代理的ping。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>紧急警报</b> </td> 
   <td colname="col2"> 从cs-uri-查询(ad)值构建的数字Dimension。 它以Ping级别构建，条件是cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警报关闭</b> </td> 
   <td colname="col2"> 从cs-uri-查询(ac)值构建的数值Dimension。 它以Ping级别构建，条件是cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警报警告</b> </td> 
   <td colname="col2"> 从cs-uri-查询(ae)值构建的数值Dimension。 它以Ping级别构建，条件是cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何用户档案重新处理</b> </td> 
   <td colname="col2"> 从cs-uri-查询(aa)值构建的数值Dimension。 它构建在Ping级别，条件是cs-uri-查询(a)与“1”匹配，cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截至延迟分钟数</b> </td> 
   <td colname="col2"> cs-uri-查询(bi)被置于x-as-of-delay-minutes字段中，并舍入到最近的分钟。 它以Ping级别构建，条件是cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行百分比</b> </td> 
   <td colname="col2"> 从cs-uri-查询(r)值构建的数值Dimension。 它构建在Ping级别，条件是cs-uri-查询(a)与“1”匹配，cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> 从cs-uri-查询(n)值构建的数值Dimension。 它构建在Ping级别，条件是cs-uri-查询(a)与“1”匹配，cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查成功</b> </td> 
   <td colname="col2"> 从cs-uri-查询(v)值构建的简单Dimension。 它构建在Ping级别，并且条件是cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件出错</b> </td> 
   <td colname="col2"> cs-uri-查询(ao)由"|"分隔符拆分，并复制到x-components-in-error字段中。 从x-components-in-error字段构建的“多到多”Dimension。 在Ping级别构建。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>详细检查秒数</b> </td> 
   <td colname="col2"> 从cs-uri-查询(l)值构建的数值Dimension。 它构建在Ping级别，条件是cs-uri-查询(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>详细检查成功</b> </td> 
   <td colname="col2"> 使用cs-uri-查询(k)值构建的简单Dimension。 它以Ping级别构建，条件是cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-查询(bc)被复制到x-dimension-gbs字段中。 x-dimension-gbs字段是此简单Dimension的用户，条件为cs-uri-查询(a)匹配“2”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁盘"x"已用百分比</b> </td> 
   <td colname="col2"> 这些数值Dimension是从cs-uri-查询(ah， ai， aj， ak， al)值配置的。 它们以Ping级别构建，并以cs-uri-查询(a)匹配“1”和cs-uri-查询(k)不为空为条件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描秒数</b> </td> 
   <td colname="col2"> x-estimated-sweep-dekaseconds字段用于此数字Dimension。 这是服务器的估计扫描时间除以十（降低扫描测量分辨率以使尺寸更合理）。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入兆字节</b> </td> 
   <td colname="col2"> cs-uri-查询(bj)值用于此维。 块的最后一行用作维的值。 如果Dimension集在“快速输入”中，则此数值数据的值将显示系统输入数据时每分钟的MB。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并兆字节</b> </td> 
   <td colname="col2">cs-uri-查询(bk)值用于此维。 块的最后一行用作维的值。 如果Dimension集位于“快速合并此数值”中，则系统每分钟将显示MB。 <p><p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2">cs-uri-查询(bg)值用于此维。 该值除以1000，并四舍五入到最接近的整数。 此数字Dimension的值将显示数据集中的字段正在使用的空间量。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 从cs-uri-查询(x)值在Ping级别构建的简单Dimension。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主机</b> </td> 
   <td colname="col2"> cs-uri-查询(b)值用于此维。 Simple维的值是块的最后一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2"> x-unixtime字段被复制到x-last-ping中并除以10以减少基数。 数字Dimension在块级别构建，并使用x-last-ping字段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>负载平均</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-查询(i)值的最后一行的数值维。 它以cs-uri-查询(k)不为空为条件。 此维度用于计算所监视系统中服务器的平均负载。 <p><p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志读取百分比</b> </td> 
   <td colname="col2">cs-uri-查询(be)值用于在Ping级别构建的此数字维度。 此维度用于计算读取日志的百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件百分比</b> </td> 
   <td colname="col2"> 这是使用cs-uri-查询(o)值的数值维，在Ping级别构建。 其条件是cs-uri-查询(k)不为空，cs-uri-查询(a)匹配“1”。 此维度用于计算页面文件内存使用百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理MegaBytes总数</b> </td> 
   <td colname="col2">这是使用cs-uri-查询(ag)值的数值维，在Ping级别构建。 它的条件是cs-uri-查询(k)不为空，cs-uri-查询(a)匹配“1”。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理百分比</b> </td> 
   <td colname="col2">这是使用cs-uri-查询(ag)值的数值维，在Ping级别构建。 它的条件是cs-uri-查询(k)不为空，cs-uri-查询(a)匹配“1”。 此维度用于计算每台服务器的物理内存使用百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询百分比</b> </td> 
   <td colname="col2"> 这是使用Ping级别的cs-uri-查询值的数值维。 它的条件是cs-uri-查询(k)不为空，cs-uri-查询(a)匹配“1”。 此维度用于计算每个服务器的查询内存使用百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是使用在Ping级别构建的cs-uri-查询(q)值的数值维。 它的条件是cs-uri-查询(k)不为空，cs-uri-查询(a)匹配“1”。 它用于显示给定服务器的网络连接数。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>输出行</b> </td> 
   <td colname="col2"> cs-uri-查询(bh)值被100000除，并复制到x-output-rows字段中以减小尺寸。 X-output-rows用于在Ping级别构建的数值Dimension，条件是cs-uri-查询(a)与"2"匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping类型ID</b> </td> 
   <td colname="col2"> 使用Ping级别的cs-uri-查询(a)值构建的简单Dimension。 这显示了录制的Ping类型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轮询延迟秒数</b> </td> 
   <td colname="col2">cs-uri-查询(m)值除以10以减小维度大小，并复制到x-poll-latency-centiseconds字段中。 这是在Ping级别构建的数值维度，条件是cs-uri-查询(k)不为空，cs-uri-查询(a)与"1"匹配/此维度用于计算轮询延迟。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理模式ID</b> </td> 
   <td colname="col2"> cs-uri-查询(bb)值用于在Ping级别构建的此简单Dimension。 它的条件是cs-uri-查询(bb)不为空，并且cs-uri-查询(a)与"2"处理模式ID匹配，使用户能够查看系统处理的模式（快速输入、快速合并、实时）。 <p>注意： 该维度会隐藏，然后在客户端维度处理模式中使用友好值重新显示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>用户档案</b> </td> 
   <td colname="col2"> cs-uri-查询(ba)值用于此简单Dimension，它是在Ping级别构建的。 此维度显示当前正在监视的用户档案的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查秒数</b> </td> 
   <td colname="col2"> cs-uri-查询(h)值用于此数值Dimension。 它以Ping级别构建，条件是cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查成功</b> </td> 
   <td colname="col2"> 这是从在Ping级别构建的cs-uri-查询(g)值构建的简单维度。 它用于计算快速检查量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>实时处理百分比</b> </td> 
   <td colname="col2"> 使用在Ping级别构建的cs-uri-查询(t)值的数字Dimension。 它的条件是cs-uri-查询(a)与"1"匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>源最后</b> </td> 
   <td colname="col2"> 从在Ping级别构建的cs-uri-查询(bl)值构建的简单Dimension。 此维度显示上次与数据源联系的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库空间百分比</b> </td> 
   <td colname="col2">使用cs-uri-查询(an)值构建的数字Dimension，在Ping级别构建。 它的条件是cs-uri-查询(k)不为空，cs-uri-查询(a)匹配“1”。 它用于计算给定服务器上已使用的临时数据库空间的百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换百分比</b> </td> 
   <td colname="col2">cs-uri-查询(bf)值用于此数值维度。 它是在Ping级别构建的。 此维度用于计算完成数据转换的百分比。 <p><p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版</b> </td> 
   <td colname="col2"> cs-uri-查询(ab)值用于此简单Dimension。 它构建在Ping级别，并且条件是cs-uri-查询(ab)不为空，cs-uri-查询(a)匹配“1”。 这将显示在每台服务器上运行的Data Workbench Server的版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版主</b> </td> 
   <td colname="col2"> cs-uri-查询(ab)值被拆分，主发行版值被复制到x-insight-version-major字段中。 它是在Ping级别构建的简单Dimension，并且条件是x-insight-version-major不为空，cs-uri-查询(a)与“1”匹配。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
