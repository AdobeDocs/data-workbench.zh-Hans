---
description: 以下维度可在Data Workbench“配置文件状态”配置文件中使用。
title: Data Workbench 用户档案状态配置文件中的维度
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Data Workbench 用户档案状态配置文件中的维度{#dimensions-in-the-data-workbench-profile-status-profile}

以下维度可在Data Workbench“配置文件状态”配置文件中使用。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>块</b> </td> 
   <td colname="col2"> 这是此配置中唯一可计数的，并作为所有维的根存在。 块可以被视为服务器。 它使用的是x-trackingid字段。 块ID是服务器名称加主机名的哈希，因此每个配置文件的每个服务器大约会有一个块。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟分钟数</b> </td> 
   <td colname="col2"> cs-uri-query(bi)会放入x-as-of-delay-minutes字段中，并四舍五入到最接近的分钟数。 “截止延迟分钟数”是一个数字维度，它将块的“最后一行”从x-as-of-delay-minutes取出。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>环境</b> </td> 
   <td colname="col2"> cs-uri-query(c)值用于环境ID。 块的最后一行将用作维度的值。 此简单Dimension将显示您的服务器正在运行的环境（如果已正确配置）。 <p>这可以在insight_monitor_agent.cfg文件中进行设置 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入MegaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值将用于此维度。 块的“最后一行”将用作维度的值。 如果Dimension集在“快速输入”中，则此数值数据的值将显示系统输入数据的每分钟MB。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并MegaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用于此维度。 块的最后一行将用作维度的值。 如果Dimension集处于“快速合并”中此数值数据的值将显示系统合并时每分钟的MB。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bg)值用于此维度。 该值除以1000，然后四舍五入到最接近的整数。 此数值Dimension的值将显示数据集中的字段正在使用的空间量。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主机</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用于此维度。 简单维度的值是块的最后一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2">x-last-ping是x-unixtime除以10（以适应数值维度大小限制）。 最后Ping是给定块的最后一行，它表示监视代理上次记录系统运行状况的时间。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志读取百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值用于此数值维度。 它是给定块的最后一行。 此维度用于计算读取的日志百分比。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用于此简单Dimension。 它是给定块的最后一行。 处理模式ID允许您查看系统处理的模式（快速输入、快速合并、实时）。 <p>注意： 此维度会被隐藏，然后在客户端维度处理模式中使用友好值重新显示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理停止</b> </td> 
   <td colname="col2"> x-processing-stalled字段通过各种条件创建，以指示用户档案当前是否正在运行。 这是一个简单的维度。 <p>注意： 当要在DPU之间公平分配大量输入日志时，此维度最有效。 例如，如果每天只加载一个大文件，则Data Workbench可能会显示为“停止”一小时或更长时间，从而导致从此维度读取误报。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>用户档案</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用于此简单Dimension。 此维度显示当前正在监控的用户档案的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后源</b> </td> 
   <td colname="col2"> cs-uri-query(bl)的最后一行将复制到x-source-emisted-bind字段中。 简单Dimension对给定块使用最后一行。 此维度显示上次与数据源联系的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换百分比</b> </td> 
   <td colname="col2"> cs-uri-query(bf)值用于此数值维度。 它是给定块的最后一行。 此维度用于计算完成数据转换的百分比。 <p>注意： 此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>时间维度</b> </td> 
   <td colname="col2"> 小时、日、周、月、小时和每周日期均从x-timestamp字段派生。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 对单词进行分组，以便您有另一种方法来过滤生成的数据集。 在insight_monitor_agent.cfg文件中设置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>量度</b> </td> 
   <td colname="col2"> 下面列出了Data Workbench配置文件监控配置文件中包含的量度及其派生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟分钟数</b> </td> 
   <td colname="col2"> 此量度是每个块的“截止延迟分钟数”的总和，然后除以“块”量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延迟秒数</b> </td> 
   <td colname="col2"> 此量度是每个块的“截至延迟秒数”的总和除以总块数。 (截至延迟秒数Dimension未开箱配置) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>块</b> </td> 
   <td colname="col2"> 对每个块求和一。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入MB</b> </td> 
   <td colname="col2"> 每个块的快速输入兆字节/分钟的总和除以当快速输入兆字节/分钟大于零时的块数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并MB</b> </td> 
   <td colname="col2"> 每个块的快速合并兆字节数/分钟之和除以当快速合并兆字节数/分钟大于零时的块数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2"> 每个块的字段GB除以块量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上Ping年龄</b> </td> 
   <td colname="col2"> 截止时间减去上次Ping时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping时间</b> </td> 
   <td colname="col2"> 每个块的最后Ping总和除以块，然后乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志读取</b> </td> 
   <td colname="col2"> 当日志读取百分比大于零时，日志读取是每个块的日志读取百分比除以块量度的总和，所有块除以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理停止</b> </td> 
   <td colname="col2"> 每个块的处理停止Dimension的总和，除以块量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换</b> </td> 
   <td colname="col2"> 每个块的转换百分比总和除以块量度，当转换百分比大于零时，全部除以10。 </td> 
  </tr> 
 </tbody> 
</table>
