---
description: 以下维可用于Data Workbench Server状态配置文件。
solution: Analytics
title: Data Workbench Server状态配置文件中的维
topic: Data workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench Server状态配置文件中的维{#dimensions-in-the-data-workbench-server-status-profile}

以下维可用于Data Workbench Server状态配置文件。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>服务器</b> </td> 
   <td colname="col2"> 此可计数维度是从x-trackingid字段构建的，它表示当前运行的Servers Data Workbench。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>代理版本</b> </td> 
   <td colname="col2"> cs-uri-query(af)值用于此简单维。 它是服务器的“最后一个非空值”。 这会显示运行的监视代理的版本的构建日期和时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何配置文件重新处理</b> </td> 
   <td colname="col2"> cs-uri-query(aa)字段用于此数字维，它是给定服务器的最后一行的值，条件是cs-uri-query(k)不为空。 此维用于指示是否有任何配置文件正在重新处理。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行百分比</b> </td> 
   <td colname="col2"> cs-uri-query(r)字段用于此数字维，它是给定服务器的最后一行的值，条件是cs-uri-query(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> cs-uri-query(n)字段用于此数字维，它是给定服务器的最后一行的值，条件是cs-uri-query(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>通用名称</b> </td> 
   <td colname="col2"> sc-ur-query(am)字段用于此简单维，它是给定服务器的最后一个非空值的值。 它显示所监视服务器的通用名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)字段用于此简单维，它是给定服务器的最后一行的值。 此维检查服务器的组件，以验证它们是否正常运行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>错误组件</b> </td> 
   <td colname="col2"> Crossrows转换获取cs-uri-query(ao)的“最后一行”值，并将其复制到x-components-in-error字段中。 此“多到多”维在被监视的服务器上显示出错误的任何组件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>环境</b> </td> 
   <td colname="col2">cs-uri-query(c)值用于环境ID。 块的最后一行用作维的值。 此简单维度将显示您的服务器正在其中运行的环境（前提是正确配置）。 <p><p>注意： 此维度在insight_monitor_agent.cfg中设置。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描秒数</b> </td> 
   <td colname="col2"> x-estimated-sweep-dekaseconds字段用于此数字维度。 这是服务器的估计扫描时间除以十（降低扫描测量分辨率以使尺寸更合理）。 <p><p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用于此维。 “简单”维的值是块的“最后一行”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2"> x-last-ping是x-unixtime除以10（以适应数字尺寸大小限制）。 最后Ping是给定块的最后一行，它表示监视代理上次记录系统运行状况的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>负载平均值</b> </td> 
   <td colname="col2"> 这是一个数值维，它使用给定服务器的cs-uri-query(i)值的最后一行。 它受cs-uri-query(k)不为空的条件。 此维度用于计算所监视系统中服务器的平均负载。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件百分比</b> </td> 
   <td colname="col2"> 这是一个数值维，它使用给定服务器的cs-uri-query(o)值的最后一行。 它受cs-uri-query(k)不为空的条件。 此维度用于计算页面文件内存使用的百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理兆字节总数</b> </td> 
   <td colname="col2"> 这是一个数值维，它使用给定服务器的cs-uri-query(ag)值的最后一行。 它受cs-uri-query(k)不为空的条件。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理百分比</b> </td> 
   <td colname="col2"> 这是一个数值维，它使用给定服务器的cs-uri-query(ag)值的最后一行。 它受cs-uri-query(k)不为空的条件。 此维度用于计算每台服务器的物理内存使用百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询百分比</b> </td> 
   <td colname="col2"> 这是一个数值维，它使用给定服务器的cs-uri-query值的最后一行。 它受cs-uri-query(k)不为空的条件。 此维度用于计算每个服务器的查询内存使用百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是一个数值维，它使用给定服务器的cs-uri-query(q)值的“最后一行”。 它受cs-uri-query(k)不为空的条件。 它用于显示给定服务器的网络连接数。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>投票延迟厘秒</b> </td> 
   <td colname="col2"> 此维度用于计算轮询延迟。 cs-uri-query(m)值除以10以减小维度大小，并复制到x-poll-latency-centiseconds字段中。 这是一个数值维，它为给定服务器取最后一行。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查成功</b> </td> 
   <td colname="col2"> 这是一个简单维，它根据给定服务器的最后一行的cs-uri-query(g)值构建。 它用于计算快速检查度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库空间百分比</b> </td> 
   <td colname="col2"> cs-uri-query(an)值的最后一行被复制到x-temp-db-space-percentage字段中。 这是一个数值维度，用于计算给定服务器上使用的临时数据库空间的百分比。 <p>注意： 此维是隐藏的，因为只有在平均到度量中时才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight版本</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用于此简单维。 它是服务器的“最后一个非空值”。 这会显示每台服务器上运行的Data Workbench Server的版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 通过分组单词，您可以通过另一种方式筛选生成的数据集。 <p>注意： 此维度在insight_monitor_agent.cfg中设置。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>量度</b> </td> 
   <td colname="col2"> 以下列出了数据工作台配置文件监视配置文件中包含的指标及其派生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>总体容量</b> </td> 
   <td colname="col2"> 这是“容量大小”量度乘以2，再加上“容量行”量度除以3。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行</b> </td> 
   <td colname="col2"> 这是每台服务器的容量行百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小</b> </td> 
   <td colname="col2"> 这是每个服务器的容量大小百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查</b> </td> 
   <td colname="col2"> 这是组件检查成功等于1的服务器数，除以服务为DPU或FSU的服务器，全部乘以100（以使其占百分比）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁盘“x”</b> </td> 
   <td colname="col2"> 磁盘度量的计算方法是将每台服务器的磁盘使用百分比的总和除以服务器度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描分钟数</b> </td> 
   <td colname="col2"> 这是每台服务器的估计扫描秒数的总和除以服务器度量，其中估计扫描秒数大于零，全部除以6。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping时间</b> </td> 
   <td colname="col2"> 每个块的最后Ping总和除以块，再乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>加载</b> </td> 
   <td colname="col2"> 这是每台服务器的平均负载除以服务器度量的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件</b> </td> 
   <td colname="col2"> 这是每台服务器的内存页面文件百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>物理内存</b> </td> 
   <td colname="col2"> 这是每台服务器的内存物理百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询</b> </td> 
   <td colname="col2"> 这是每台服务器的内存查询百分比除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是每个服务器的网络连接总和除以服务器度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>投票延迟（毫秒）</b> </td> 
   <td colname="col2"> 这是每个服务器的轮询延迟厘秒数的总和除以服务器度量，所有这些度量乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查</b> </td> 
   <td colname="col2"> 这是“快速检查成功率”等于1的服务器数除以“服务器”量度，其中所有服务器数均乘以100。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>服务器</b> </td> 
   <td colname="col2"> 这是每台服务器的1或被监视服务器的总数之和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库</b> </td> 
   <td colname="col2"> 这是每台服务器的临时数据库空间百分比除以服务器度量的总和。 </td> 
  </tr> 
 </tbody> 
</table>

