---
description: 以下维可用于Data Workbench配置文件状态配置文件。
solution: Analytics
title: 数据工作台配置文件状态配置文件中的维
topic: Data workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 数据工作台配置文件状态配置文件中的维{#dimensions-in-the-data-workbench-profile-status-profile}

以下维可用于Data Workbench配置文件状态配置文件。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>块</b> </td> 
   <td colname="col2"> 这是此配置中唯一可计数的，它作为所有维的根存在。 块可以视为服务器。 它使用x-trackingid字段。 块ID是服务器名加主机名的哈希值，因此每个配置文件每个服务器大约有一个块。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟分钟数</b> </td> 
   <td colname="col2"> cs-uri-query(bi)被放置到x-as-of-delay-minutes字段中，并舍入到最近的分钟数。 “截止延迟分钟数”是一个数字维度，该维度将块的“最后一行”从x-as-of-delay-minutes变为“最后一行”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>环境</b> </td> 
   <td colname="col2"> cs-uri-query(c)值用于环境ID。 块的最后一行用作维的值。 此简单维度将显示您的服务器正在其中运行的环境（前提是正确配置）。 <p>可以在insight_monitor_agent.cfg文件中设置 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入兆字节数</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值用于此维。 块的最后一行用作维的值。 如果数据集在“快速输入”中，则此数字维度的值将显示系统输入数据的每分钟MB。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并兆字节</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用于此维。 块的最后一行用作维的值。 如果数据集位于“快速合并此数字维度”值中，则将显示系统合并时的每分钟MB。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bg)值用于此维。 该值除以1000，并舍入到最接近的整数。 此数值维度的值将显示数据集中“字段”使用的空间量。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用于此维。 “简单”维的值是块的“最后一行”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2">x-last-ping是x-unixtime除以10（以适应数字尺寸大小限制）。 最后Ping是给定块的最后一行，它表示监视代理上次记录系统运行状况的时间。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志阅读百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值用于此数字维。 它是给定块的最后一行。 此维度用于计算读取日志的百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用于此简单维。 它是给定块的最后一行。 处理模式ID允许用户查看系统处理的模式（快速输入、快速合并、实时）。 <p>注意： 该维是隐藏的，然后在客户端维处理模式中使用友好值重新显示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理已停止</b> </td> 
   <td colname="col2"> x-processing-stalted字段是通过各种条件创建的，以指示配置文件当前是否正在运行。 这是一个简单的维度。 <p>注意： 当在DPU之间有大量输入日志要公平分配时，此维度最有效。 例如，如果每天只加载一个大文件，则Data Workbench可能会“停止”一小时或更长时间，从而导致从该维度读取错误正数。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>配置文件</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用于此简单维。 此维显示当前正在监视的配置文件的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>源最后</b> </td> 
   <td colname="col2"> cs-uri-query(bl)的最后一行被复制到x-source-emestive-beind字段中。 Simple Dimension对给定块使用Last Row。 此维度显示上次与数据源联系的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换百分比</b> </td> 
   <td colname="col2"> cs-uri-query(bf)值用于此数字维。 它是给定块的最后一行。 此维用于计算完成数据转换的百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>时间维度</b> </td> 
   <td colname="col2"> 小时、日、周、月、小时和周日均来自x-timestamp字段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 通过分组单词，您可以通过另一种方式筛选生成的数据集。 在insight_monitor_agent.cfg文件中设置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>量度</b> </td> 
   <td colname="col2"> 以下列出了数据工作台配置文件监视配置文件中包含的指标及其派生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟分钟数</b> </td> 
   <td colname="col2"> 此度量是每个块的“截止延迟分钟数”之和，然后除以“块”度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟秒数</b> </td> 
   <td colname="col2"> 此度量是每个块的“截止延迟秒数”的和，除以总块数。 （截止到延迟秒数维度未开箱配置） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>块</b> </td> 
   <td colname="col2"> 为每个块求和一个。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入MB</b> </td> 
   <td colname="col2"> 当“快速输入兆字节／分钟”大于零时，每个块的“快速输入兆字节／分钟”除以“块数”的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并MB</b> </td> 
   <td colname="col2"> 当“快速合并兆字节”每分钟大于零时，每个块的“快速合并兆字节”总数除以“块数”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2"> 每个块的字段GB总和除以块度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Age</b> </td> 
   <td colname="col2"> 截止时间减去上次Ping时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping时间</b> </td> 
   <td colname="col2"> 每个块的最后Ping总和除以块，再乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志读取</b> </td> 
   <td colname="col2"> 如果“日志阅读百分比”大于零，则“日志阅读百分比”是每个块的“日志阅读百分比”之和，除以“块”量度，所有块除以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理已停止</b> </td> 
   <td colname="col2"> 每个块的处理停止维的和，除以块度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换</b> </td> 
   <td colname="col2"> 当“转换百分比”大于零时，每个块的“转换百分比”除以“块”量度的总和，全部除以10。 </td> 
  </tr> 
 </tbody> 
</table>

