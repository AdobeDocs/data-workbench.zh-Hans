---
description: 以下维可用于Data Workbench用户档案状态用户档案。
title: Data Workbench 用户档案状态配置文件中的维度
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Data Workbench 用户档案状态配置文件中的维度{#dimensions-in-the-data-workbench-profile-status-profile}

以下维可用于Data Workbench用户档案状态用户档案。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>阻止</b> </td> 
   <td colname="col2"> 这是此配置中唯一可计数的，并作为所有维的根存在。 块可以视为服务器。 它使用x-trackingid字段。 块ID是服务器名称加主机名的哈希值，因此每个用户档案每个服务器大约有一个块。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截至延迟分钟数</b> </td> 
   <td colname="col2"> cs-uri-查询(bi)被置于x-as-of-delay-minutes字段中，并舍入到最近的分钟。 “截止延迟分钟数”是一个数字维度，它将块的“最后一行”从x-as-of-delay-minutes中取消。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>环境</b> </td> 
   <td colname="col2"> cs-uri-查询(c)值用于环境ID。 块的最后一行用作维的值。 此简单Dimension将显示您的服务器运行的环境（如果配置正确）。 <p>可以在insight_monitor_agent.cfg文件中设置 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入兆字节</b> </td> 
   <td colname="col2"> cs-uri-查询(bj)值用于此维。 块的最后一行用作维的值。 如果Dimension集在“快速输入”中，则此数值数据的值将显示系统输入数据时每分钟的MB。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并兆字节</b> </td> 
   <td colname="col2">cs-uri-查询(bk)值用于此维。 块的最后一行用作维的值。 如果Dimension集位于“快速合并此数值”中，则系统每分钟将显示MB。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-查询(bg)值用于此维。 该值除以1000，并四舍五入到最接近的整数。 此数字Dimension的值将显示数据集中的字段正在使用的空间量。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主机</b> </td> 
   <td colname="col2"> cs-uri-查询(b)值用于此维。 Simple维的值是块的最后一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2">x-last-ping是x-unixtime除以10（以适应数值尺寸大小约束）。 Last Ping是给定块的最后一行，它表示监视代理上次记录系统运行状况的时间。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志读取百分比</b> </td> 
   <td colname="col2">cs-uri-查询(be)值用于此数值维度。 它是给定块的最后一行。 此维度用于计算读取日志的百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理模式ID</b> </td> 
   <td colname="col2"> cs-uri-查询(bb)值用于此简单Dimension。 它是给定块的最后一行。 “处理模式ID”允许您查看处理系统的模式（“快速输入”、“快速合并”、“实时”）。 <p>注意： 该维度会隐藏，然后在客户端维度处理模式中使用友好值重新显示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理已停止</b> </td> 
   <td colname="col2"> x-processing-stalet字段通过各种条件创建，以指示用户档案当前是否正在运行。 这是一个简单的维度。 <p>注意： 当在DPU之间公平分布大量输入日志时，此维度最有效。 例如，如果每天只加载一个大文件，则Data Workbench可能显示为“停止”一小时或更长时间，导致从此维度读取错误正数。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>用户档案</b> </td> 
   <td colname="col2"> cs-uri-查询(ba)值用于此简单Dimension。 此维显示当前正在监视的用户档案的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>源最后</b> </td> 
   <td colname="col2"> cs-uri-查询(bl)的最后一行被复制到x-source-emestive-beind字段中。 “简单”Dimension对给定块使用“最后一行”。 此维度显示上次与数据源联系的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换百分比</b> </td> 
   <td colname="col2"> cs-uri-查询(bf)值用于此数值维度。 它是给定块的最后一行。 此维度用于计算完成数据转换的百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>时间维度</b> </td> 
   <td colname="col2"> “小时”、“天”、“周”、“月”、“小时”和“星期”均来自x-timestamp字段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 通过分组单词，您可以通过其他方式筛选生成的数据集。 在insight_monitor_agent.cfg文件中设置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指标</b> </td> 
   <td colname="col2"> 以下列表了Data Workbench用户档案监控用户档案中包含的量度及其派生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截至延迟分钟</b> </td> 
   <td colname="col2"> 此量度是每个块的延迟分钟数的总和，然后除以块量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>延迟秒数</b> </td> 
   <td colname="col2"> 此量度是每个块的“延迟秒数”的总和，除以块总数。 (从“延迟秒数”Dimension开箱后未配置) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>块</b> </td> 
   <td colname="col2"> 每个块求和一个。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速输入MB</b> </td> 
   <td colname="col2"> 当快速输入每分钟兆字节数大于零时，每个块的快速输入兆字节数除以块数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分钟快速合并MB</b> </td> 
   <td colname="col2"> 当“快速合并兆字节/分钟”大于零时，每个块的快速合并兆字节/分钟总和除以块数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>字段GigaBytes</b> </td> 
   <td colname="col2"> 每个块的字段GB总和除以块量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上Ping年代</b> </td> 
   <td colname="col2"> 截止时间减去上次Ping时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping时间</b> </td> 
   <td colname="col2"> 每个块的最后Ping总和除以块，再乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日志读取</b> </td> 
   <td colname="col2"> 如果“日志阅读百分比”大于零，则“日志阅读百分比”是每个块的“日志阅读百分比”之和，除以块量度，所有块除以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>处理已停止</b> </td> 
   <td colname="col2"> 每个块的处理停止Dimension总和，除以块量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>转换</b> </td> 
   <td colname="col2"> 每个块的“转换百分比”和“块”量度（当“转换百分比”大于零时，全部除以10）之和。 </td> 
  </tr> 
 </tbody> 
</table>
