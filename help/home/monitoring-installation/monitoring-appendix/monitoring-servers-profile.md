---
description: 以下维可在Data Workbench Server状态用户档案中使用。
title: Data Workbench 服务器状态配置文件中的维度
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Data Workbench 服务器状态配置文件中的维度{#dimensions-in-the-data-workbench-server-status-profile}

以下维可在Data Workbench Server状态用户档案中使用。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>服务器</b> </td> 
   <td colname="col2"> 此可计数维度是从x-trackingid字段构建的，它表示当前运行Data Workbench的服务器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>代理版本</b> </td> 
   <td colname="col2"> cs-uri-查询(af)值用于此简单Dimension。 它是服务器的最后一个非空值。 这将显示运行的监视代理版本的生成日期和时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何用户档案重新处理</b> </td> 
   <td colname="col2"> cs-uri-查询(aa)字段用于此数值Dimension，它是给定服务器的最后一行的值，条件是cs-uri-查询(k)不为空。 此维用于指示是否有任何用户档案正在重新处理。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行百分比</b> </td> 
   <td colname="col2"> cs-uri-查询(r)字段用于此数值Dimension，它是给定服务器的最后一行的值，条件是cs-uri-查询(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> cs-uri-查询(n)字段用于此数值Dimension，它是给定服务器的最后一行的值，条件是cs-uri-查询(k)不为空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>通用名称</b> </td> 
   <td colname="col2"> sc-ur-查询(am)字段用于此简单Dimension，它是给定服务器的Last Nonblank值的值。 它显示被监视服务器的“公用名称”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件检查成功</b> </td> 
   <td colname="col2"> cs-uri-查询(v)字段用于此简单Dimension，它是给定服务器的最后一行的值。 此维度检查服务器的组件，以验证它们是否正常工作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>组件出错</b> </td> 
   <td colname="col2"> Crossrows转换将获取cs-uri-查询(ao)的Last Row值，并将其复制到x-components-in-error字段中。 此“多到多”维度在被监视的服务器上显示出错误的任何组件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>环境</b> </td> 
   <td colname="col2">cs-uri-查询(c)值用于环境ID。 块的最后一行用作维的值。 此简单Dimension将显示您的服务器运行的环境（如果配置正确）。 <p><p>注意： 此维度在insight_monitor_agent.cfg中设置。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描秒数</b> </td> 
   <td colname="col2"> x-estimated-sweep-dekaseconds字段用于此数字Dimension。 这是服务器的估计扫描时间除以十（降低扫描测量分辨率以使尺寸更合理）。 <p><p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主机</b> </td> 
   <td colname="col2"> cs-uri-查询(b)值用于此维。 Simple维的值是块的最后一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最后Ping</b> </td> 
   <td colname="col2"> x-last-ping是x-unixtime除以10（以适应数值尺寸大小约束）。 Last Ping是给定块的最后一行，它表示监视代理上次记录系统运行状况的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>负载平均</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-查询(i)值的最后一行的数值维。 它以cs-uri-查询(k)不为空为条件。 此维度用于计算所监视系统中服务器的平均负载。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件百分比</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-查询(o)值的最后一行的数值维。 它以cs-uri-查询(k)不为空为条件。 此维度用于计算页面文件内存使用百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理MegaBytes总数</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-查询(ag)值的最后一行的数值维。 它以cs-uri-查询(k)不为空为条件。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存物理百分比</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-查询(ag)值的最后一行的数值维。 它以cs-uri-查询(k)不为空为条件。 此维度用于计算每台服务器的物理内存使用百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存查询百分比</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-查询值的最后一行的数值维。 它以cs-uri-查询(k)不为空为条件。 此维度用于计算每个服务器的查询内存使用百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>网络连接</b> </td> 
   <td colname="col2"> 这是使用给定服务器的cs-uri-查询(q)值的最后一行的数值维。 它以cs-uri-查询(k)不为空为条件。 它用于显示给定服务器的网络连接数。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轮询延迟秒数</b> </td> 
   <td colname="col2"> 此维度用于计算轮询延迟。 cs-uri-查询(m)值除以10以减小维度大小，并复制到x-poll-latency-centiseconds字段中。 这是一个数值维度，它取给定服务器的最后一行。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查成功</b> </td> 
   <td colname="col2"> 这是一个简单维度，它基于给定服务器的最后一行的cs-uri-查询(g)值构建。 它用于计算快速检查量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库空间百分比</b> </td> 
   <td colname="col2"> cs-uri-查询(an)值的最后一行将复制到x-temp-db-space-percentage字段中。 这是一个数值Dimension，用于计算给定服务器上已使用的临时数据库空间的百分比。 <p>注意： 此维度是隐藏的，因为只有在平均到量度时，此维度才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight版本</b> </td> 
   <td colname="col2"> cs-uri-查询(ab)值用于此简单Dimension。 它是服务器的最后一个非空值。 这将显示在每台服务器上运行的Data Workbench Server的版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群组</b> </td> 
   <td colname="col2"> 通过分组单词，您可以通过其他方式筛选生成的数据集。 <p>注意： 此维度在insight_monitor_agent.cfg中设置。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指标</b> </td> 
   <td colname="col2"> 以下列表了Data Workbench用户档案监控用户档案中包含的量度及其派生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>总体容量</b> </td> 
   <td colname="col2"> 这是“容量大小”量度乘以2加上“容量行”量度除以3。 </td> 
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
   <td colname="col2"> 这是组件检查成功等于1的服务器数，除以服务为DPU或FSU的服务器，全部乘以100（以百分比表示）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁盘"x"</b> </td> 
   <td colname="col2"> 磁盘量度的计算方法是将每台服务器的磁盘使用百分比的总和除以服务器量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估计扫描分钟数</b> </td> 
   <td colname="col2"> 这是每个服务器的估计扫描秒数之和，除以“估计扫描秒数”大于零的“服务器”量度，全部除以6。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping时间</b> </td> 
   <td colname="col2"> 每个块的最后Ping总和除以块，再乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>加载</b> </td> 
   <td colname="col2"> 这是每个服务器的平均负载除以服务器量度的总和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>内存页文件</b> </td> 
   <td colname="col2"> 这是每个服务器的内存页文件百分比除以服务器量度的总和。 </td> 
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
   <td colname="col1"> <b>轮询延迟毫秒</b> </td> 
   <td colname="col2"> 这是每个服务器的轮询延迟秒数的总和，除以服务器量度，所有量度乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速检查</b> </td> 
   <td colname="col2"> 这是“快速检查成功”等于1的服务器数，除以“服务器”量度，所有量度均乘以100。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>服务器</b> </td> 
   <td colname="col2"> 这是每个服务器的1或被监视服务器总数之和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>临时数据库</b> </td> 
   <td colname="col2"> 这是每个服务器的临时数据库空间百分比除以服务器量度的总和。 </td> 
  </tr> 
 </tbody> 
</table>
