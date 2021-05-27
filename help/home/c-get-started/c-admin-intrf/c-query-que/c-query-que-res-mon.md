---
description: 该资源监视器矢量包含内存预算监视器和查询数量监视器。
title: 查询队列资源监视器
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 100%

---

# 查询队列资源监视器{#query-queue-resource-monitors}

该资源监视器矢量包含内存预算监视器和查询数量监视器。

下表介绍了用于查询排队的资源监视器字段。

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Memory Budget Monitor（内存预算监视器） </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>监视由当前用户组使用的查询内存。如果当前使用量介于 Low Threshold（低阈值）和 High Threshold（高阈值）之间，则在内存使用量返回到 Low Threshold（低阈值）值（例如用户关闭其工作区）以下之前不会计划新的束。允许计划的束增长。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>High Threshold（高阈值） </p> </td> 
   <td colname="col2"> <p>双精度 </p> </td> 
   <td colname="col3"> <p>内存使用量的高阈值（字节）。如果内存使用量高于该值，则不会产生任何计划，并且在一段时间内一次取消一个具有最低优先级的计划束，直到内存使用量被降低到该值以下为止。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Low Threshold（低阈值） </p> </td> 
   <td colname="col2"> <p>双精度 </p> </td> 
   <td colname="col3"> <p>内存使用量的低阈值（字节）。如果 <span class="wintitle">Memory Budget Monitor</span>（内存预算监视器）值低于该值，则允许计划新束，并且允许计划的束增长。例如，束会在用户向工作区添加可视化时增长。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reaction Time（反应时间） </p> </td> 
   <td colname="col2"> <p>双精度 </p> </td> 
   <td colname="col3"> <p>平稳内存使用估计量的时间常量。平稳值可避免使用量达到尖峰时引起的反应。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number of Queries Monitor（查询数量监视器） </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>监视当前为配置文件计划的查询总量。如果查询总数一直低于 Low Threshold（低阈值）字段中的值，则该资源监视器允许您计划束。如果查询总数一直低于 High Threshold（高阈值）字段中的值，则该监视器允许当前计划的束增长。此外，该监视器会删除多个低优先级的束，从而允许较高优先级的束列入计划或增长。但是，该设置不会抢占优先级大于 Untouchable Priority（不容更改的优先级）字段中指定值的束。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>High Threshold（高阈值） </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>内存使用量的高阈值（字节）。如果内存使用量高于该值，则不会产生任何计划，并且在一段时间内一次取消一个具有最低优先级的计划束，直到内存使用量被降低到该值以下为止。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Low Threshold（低阈值） </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>内存使用量的低阈值（字节）。如果 <span class="wintitle">Memory Budget Monitor</span>（内存预算监视器）值低于该值，则可以计划新束，并且计划的束可以增长。 </p> </td> 
  </tr> 
 </tbody> 
</table>
