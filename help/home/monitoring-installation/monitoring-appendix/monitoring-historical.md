---
description: 以下维可用于Data Workbench历史配置文件。
solution: Analytics
title: 数据工作台历史配置文件中的维
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 数据工作台历史配置文件中的维{#dimensions-in-the-data-workbench-historic-profile}

以下维可用于Data Workbench历史配置文件。

## 数据工作台历史配置文件中的维 {#section-96f1b64f5cb84411b630f97f227d888d}

以下维可用于Data Workbench历史配置文件。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>块</b> </td> 
   <td colname="col2">这是此配置中唯一可计数的，它是所有维的根。 块可以视为服务器。 它使用x-trackingid字段。 <p>注意： 块ID是服务器名加主机名的哈希值，因此每个配置文件每个服务器大约有一个块。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> 这是由块可数构成的可数维。 配置文件中的每一行数据都是来自监视代理的ping。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>紧急警报</b> </td> 
   <td colname="col2"> 从cs-uri-query(ad)值构建的数字维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警报关闭</b> </td> 
   <td colname="col2"> 从cs-uri-query(ac)值构建的数字维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警报警告</b> </td> 
   <td colname="col2"> 从cs-uri-query(ae)值构建的数值维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何配置文件重新处理</b> </td> 
   <td colname="col2"> 从cs-uri-query(aa)值构建的数字维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配且cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟分钟数</b> </td> 
   <td colname="col2"> cs-uri-query(bi)被放置到x-as-of-delay-minutes字段中，并舍入到最近的分钟数。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行百分比</b> </td> 
   <td colname="col2"> 从cs-uri-query(r)值构建的数字维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配且cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> 从cs-uri-query(n)值构建的数字维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配且cs-uriquery(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查成功</b> </td> 
   <td colname="col2"> 从cs-uri-query(v)值构建的简单维。 它构建于Ping级别，并且条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>错误组件</b> </td> 
   <td colname="col2"> cs-uri-query(ao)由“|”分隔符拆分，并复制到x-components-in-error字段中。 从x-components-in-error字段构建的“多维度”到“多维度”。 构建于Ping级别。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>详细检查秒数</b> </td> 
   <td colname="col2"> 从cs-uri-query(l)值构建的数字维。 它构建于Ping级别，条件是cs-uri-query(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>详细检查成功情况</b> </td> 
   <td colname="col2"> 从cs-uri-query(k)值构建的简单维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc)被复制到x-dimension-gbgs字段中。 x-dimension-gigbts字段是此Simple Dimension的用户，条件是cs-uri-query(a)匹配“2”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁盘“x”已使用百分比</b> </td> 
   <td colname="col2"> 这些数字维是根据cs-uri-query(ah, ai, aj, ak, al)值配置的。 它们在Ping级别构建，并且cs-uri-query(a)与“1”匹配且cs-uri-query(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描秒数</b> </td> 
   <td colname="col2"> x-estimated-sweep-dekaseconds字段用于此数字维度。 这是服务器的估计扫描时间除以十（降低扫描测量分辨率以使尺寸更合理）。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入兆字节数</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值用于此维。 块的最后一行用作维的值。 如果数据集在“快速输入”中，则此数字维度的值将显示系统输入数据的每分钟MB。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并兆字节</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用于此维。 块的最后一行用作维的值。 如果数据集位于“快速合并此数字维度”值中，则将显示系统合并时的每分钟MB。 <p><p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bg)值用于此维。 该值除以1000，并舍入到最接近的整数。 此数值维度的值将显示数据集中“字段”使用的空间量。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 从cs-uri-query(x)值在Ping级别构建的简单维。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用于此维。 “简单”维的值是块的“最后一行”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2"> x-unixtime字段被复制到x-last-ping中并除以10以减少基数。 数字维是在块级别构建的，并使用x-last-ping字段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>负载平均值</b> </td> 
   <td colname="col2"> 这是一个数值维，它使用给定服务器的cs-uri-query(i)值的最后一行。 它受cs-uri-query(k)不为空的条件。 此维度用于计算所监视系统中服务器的平均负载。 <p><p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志阅读百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值用于此数字维，在Ping级别构建。 此维度用于计算读取日志的百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件百分比</b> </td> 
   <td colname="col2"> 这是使用cs-uri-query(o)值的数值维，在Ping级别构建。 其条件是cs-uri-query(k)不为空，cs-uri-query(a)匹配“1”。 此维度用于计算页面文件内存使用的百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理兆字节总数</b> </td> 
   <td colname="col2">这是使用cs-uri-query(ag)值的数值维，在Ping级别构建。 其条件是cs-uri-query(k)不为空，cs-uri-query(a)匹配“1”。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理百分比</b> </td> 
   <td colname="col2">这是使用cs-uri-query(ag)值的数值维，在Ping级别构建。 其条件是cs-uri-query(k)不为空，cs-uri-query(a)匹配“1”。 此维度用于计算每台服务器的物理内存使用百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询百分比</b> </td> 
   <td colname="col2"> 这是使用Ping级别的cs-uri-query值的数值维。 其条件是cs-uri-query(k)不为空且cs-uri-query(a)匹配“1”。 此维度用于计算每个服务器的查询内存使用百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是使用在Ping级别构建的cs-uri-query(q)值的数值维。 其条件是cs-uri-query(k)不为空且cs-uri-query(a)匹配“1”。 它用于显示给定服务器的网络连接数。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>输出行</b> </td> 
   <td colname="col2"> cs-uri-query(bh)值除以100000，并复制到x-output-rows字段中以减小维的大小。 X-output-rows用于在Ping级别构建的数字维，条件是cs-uri-query(a)与“2”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping类型ID</b> </td> 
   <td colname="col2"> 使用Ping级别的cs-uri-query(a)值构建的简单维。 这显示了录制的Ping类型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>投票延迟厘秒</b> </td> 
   <td colname="col2">cs-uri-query(m)值除以10以减小维度大小，并复制到x-poll-latency-centiseconds字段中。 这是在Ping级别构建的数值维，条件是cs-uri-query(k)不为空，cs-uri-query(a)匹配“1”/此维用于计算轮询延迟。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用于在Ping级别构建的此简单维。 条件是cs-uri-query(bb)不为空，并且cs-uri-query(a)与“2”处理模式ID匹配，这允许用户查看系统处于何种处理模式（快速输入、快速合并、实时）。 <p>注意： 该维是隐藏的，然后在客户端维处理模式中使用友好值重新显示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>配置文件</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用于此简单维，它在Ping级别构建。 此维显示当前被监视的配置文件的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查秒数</b> </td> 
   <td colname="col2"> cs-uri-query(h)值用于此数值维。 它构建于Ping级别，条件是cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查成功</b> </td> 
   <td colname="col2"> 这是一个简单维，它根据在Ping级别构建的cs-uri-query(g)值构建。 它用于计算快速检查度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>实时处理百分比</b> </td> 
   <td colname="col2"> 使用在Ping级别构建的cs-uri-query(t)值的数值维。 cs-uri-query(a)与“1”匹配的条件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>源最后</b> </td> 
   <td colname="col2"> 从Ping级别构建的cs-uri-query(bl)值构建的简单维。 此维度显示上次与数据源联系的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库空间百分比</b> </td> 
   <td colname="col2">使用cs-uri-query(an)值构建的数字维，在Ping级别构建。 条件是cs-uri-query(k)不为空，cs-uri-query(a)匹配“1”。 它用于计算给定服务器上使用的临时数据库空间的百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换百分比</b> </td> 
   <td colname="col2">cs-uri-query(bf)值用于此数字维。 它构建于Ping级别。 此维用于计算完成数据转换的百分比。 <p><p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>数据工作台版本</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用于此简单维。 它构建于Ping级别，并且条件是cs-uri-query(ab)不为空，且cs-uri-query(a)与“1”匹配。 这会显示每台服务器上运行的Data Workbench Server的版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版本主要</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值被拆分，主发行版值被复制到x-insight-version-major字段中。 它是在Ping级别构建的一个简单维，并且条件是x-insight-version-major不为空，且cs-uri-query(a)与“1”匹配。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

