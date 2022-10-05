---
description: 以下维度可在Data Workbench服务器状态配置文件中使用。
title: Data Workbench 服务器状态配置文件中的维度
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Data Workbench 服务器状态配置文件中的维度{#dimensions-in-the-data-workbench-server-status-profile}

{{eol}}

以下维度可在Data Workbench服务器状态配置文件中使用。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>服务器</b> </td> 
   <td colname="col2"> 此可计数维度是从x-trackingid字段构建的，它表示当前运行Data Workbench的服务器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>代理版本</b> </td> 
   <td colname="col2"> cs-uri-query(af)值用于此简单Dimension。 它是服务器的最后一个非空值。 这会显示运行监视代理的版本的生成日期和时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>重新处理任何配置文件</b> </td> 
   <td colname="col2"> cs-uri-query(aa)字段用于此数值Dimension，它是给定服务器的“最后一行”的值，cs-uri-query(k)条件不为空。 此维度用于指示是否有任何用户档案正在重新处理。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>能力行百分比</b> </td> 
   <td colname="col2"> cs-uri-query(r)字段用于此数值Dimension，它是给定服务器的“最后一行”的值，cs-uri-query(k)条件不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> cs-uri-query(n)字段用于此数值Dimension，它是给定服务器的“最后一行”的值，cs-uri-query(k)条件不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>通用名称</b> </td> 
   <td colname="col2"> sc-ur-query(am)字段用于此简单Dimension，它是给定服务器的Last Nonblank值的值。 它显示受监控服务器的通用名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)字段用于此简单Dimension，它是给定服务器的“最后一行”的值。 此维度检查服务器的组件，以验证它们是否正常工作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出错的组件</b> </td> 
   <td colname="col2"> Crossrows转换获取cs-uri-query(ao)的Last Row值，并将其复制到x-components-in-error字段中。 此“多对多”维度在受监控的服务器上显示任何出错的组件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>环境</b> </td> 
   <td colname="col2">cs-uri-query(c)值用于环境ID。 块的最后一行将用作维度的值。 此简单Dimension将显示您的服务器正在运行的环境（如果已正确配置）。 <p><p>注意：此维度在insight_monitor_agent.cfg中设置。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描秒数</b> </td> 
   <td colname="col2"> 此数值Dimension中使用x-estimated-sweep-dekaseconds字段。 这是服务器的估计扫描时间除以10（降低扫描测量分辨率以使维度更合理地大小）。 <p><p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用于此维度。 简单维度的值是块的最后一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2"> x-last-ping是x-unixtime除以10（以适应数值维度大小限制）。 最后Ping是给定块的最后一行，它表示监视代理上次记录系统运行状况的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>加载平均值</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-query(i)值的最后一行的数字维度。 它以cs-uri-query(k)不为空为条件。 此维度用于计算所监视系统中服务器的平均负载。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件百分比</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-query(o)值的最后一行的数字维度。 它以cs-uri-query(k)不为空为条件。 此维度用于计算页面文件内存使用率的百分比。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理兆字节总数</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-query(ag)值的最后一行的数字维度。 它以cs-uri-query(k)不为空为条件。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理百分比</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-query(ag)值的最后一行的数字维度。 它以cs-uri-query(k)不为空为条件。 此维度用于计算每个服务器的物理内存使用率百分比。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询百分比</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-query(s)值的最后一行的数字维度。 它以cs-uri-query(k)不为空为条件。 此维度用于计算每个服务器的查询内存使用率百分比。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-query(q)值的最后一行的数字维度。 它以cs-uri-query(k)不为空为条件。 用于显示给定服务器的网络连接数。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轮询延迟厘秒</b> </td> 
   <td colname="col2"> 此维度用于计算投票延迟。 cs-uri-query(m)值除以10可减小维度大小，并复制到x-poll-latency-entiseconds字段中。 这是一个数值维度，用于获取给定服务器的最后一行。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查成功</b> </td> 
   <td colname="col2"> 这是一个简单维度，该维度是根据给定服务器的“最后一行”的cs-uri-query(g)值构建的。 它用于计算快速检查量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库空间百分比</b> </td> 
   <td colname="col2"> cs-uri-query(an)值的最后一行将复制到x-temp-db-space-percentage字段中。 这是一个数值Dimension，用于计算给定服务器上已用临时数据库空间的百分比。 <p>注意：此维度是隐藏的，因为仅当平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight版本</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用于此简单Dimension。 它是服务器的最后一个非空值。 这会显示每个服务器上运行的Data Workbench Server的版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 对单词进行分组，以便您有另一种方法来过滤生成的数据集。 <p>注意：此维度在insight_monitor_agent.cfg中设置。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指标</b> </td> 
   <td colname="col2"> 下面列出了Data Workbench配置文件监控配置文件中包含的量度及其派生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>总体容量</b> </td> 
   <td colname="col2"> 这是“容量大小”量度乘以二加上“容量行”量度除以3。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行</b> </td> 
   <td colname="col2"> 这是每个服务器的容量行百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小</b> </td> 
   <td colname="col2"> 这是每个服务器的容量大小百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查</b> </td> 
   <td colname="col2"> 这是组件检查成功等于1的服务器数，除以服务为DPU或FSU的服务器数，再乘以100（以百分比表示）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁盘"x"</b> </td> 
   <td colname="col2"> “磁盘”量度的计算方式是计算每个服务器的“磁盘使用百分比”的总和除以“服务器”量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描分钟数</b> </td> 
   <td colname="col2"> 这是每个服务器的估计扫描秒数除以估计扫描秒数大于零的服务器量度（全部除以6）的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping时间</b> </td> 
   <td colname="col2"> 每个块的最后Ping总和除以块，然后乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>加载</b> </td> 
   <td colname="col2"> 这是每个服务器的平均负载除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件</b> </td> 
   <td colname="col2"> 这是每个服务器的内存页面文件百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理</b> </td> 
   <td colname="col2"> 这是每个服务器的内存物理百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询</b> </td> 
   <td colname="col2"> 这是每个服务器的内存查询百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是每个服务器的网络连接总和除以服务器量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>投票延迟毫秒数</b> </td> 
   <td colname="col2"> 这是每个服务器的轮询延迟厘秒数的总和除以“服务器”量度，所有量度乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查</b> </td> 
   <td colname="col2"> 这是快速检查成功等于1的服务器数，除以“服务器”量度，所有量度都乘以100。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>服务器</b> </td> 
   <td colname="col2"> 这是每台服务器的总和，即受监控服务器的总数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库</b> </td> 
   <td colname="col2"> 这是每个服务器的临时数据库空间百分比除以服务器量度的总和。 </td> 
  </tr> 
 </tbody> 
</table>
