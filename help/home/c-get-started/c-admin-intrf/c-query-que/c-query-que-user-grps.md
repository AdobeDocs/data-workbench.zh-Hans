---
description: 用于定义 User Group（用户组）参数的表格。
solution: Analytics
title: 查询队列用户组
topic: Data workbench
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查询队列用户组{#query-queue-user-groups}

用于定义 User Group（用户组）参数的表格。

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>名称 </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>用户定义的用户组名称，例如 Analysts（分析师）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Policies（策略） </p> </td> 
   <td colname="col2"> <p>矢量 </p> </td> 
   <td colname="col3"> <p>指定策略类型。右键单击可选择 Standard Policy（标准策略）或 Daily Schedule（每日计划）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard Policy（标准策略） </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Standard Policy（标准策略）可确保低优先级用户在队列中逐步上升并列入计划，即使有较高优先级的用户加入队列也是如此。您可以在一个组内添加同一类型的多个策略，它们的效果是累积的。 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>优先级限制：</b>超出后优先级不会递增的限制。最大优先级值。您可以使用该值将由此策略生成的优先级保持在指定的范围内（例如，这样某些其他用户组的优先级将始终较高，或不超过 Untouchable Priority（不容更改的优先级）。 </li> 
     </ul> </p> <p> <b>Standard Policy Increments（标准策略增量）</b> </p> <p>Standard Policy（标准策略）的增量设置随时间流逝而提升查询束的优先级。这不会强制计划束，但是您可以使用这些设置优先排序等候较长时间的用户。已排队参数影响当前排队的查询（例如会因为没有足够的资源完成它们而等待）。计划参数影响正在应答的查询。查询的优先级会按照相应增量和增量间隔字段中指定的数值而提升： 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Queued Increment（排队增量）：</b>设置每次排队更新的优先级增量。此设置可确保低优先级用户在计划队列中上升。 </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Queued Increment Interval（排队增量间隔）：</b>设置排队更新之间的间隔秒数。 </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Scheduled Increment（计划增量）：</b>设置每次计划更新的优先级增量。 </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Scheduled Increment Interval（计划增量间隔）：</b>设置计划更新之间的间隔秒数。 <p> <p>注意：如果设置的排队束增量和间隔更新率高于计划束，则会导致振荡。（例如，假定您将 Queued Increment（排队增量）值设置为 100，将 Scheduled Increment（计划增量）值设置为 0，将 Queued Increment Interval（排队增量间隔）值设置为 1，并将 Untouchable Priority（不容更改的优先级）值设置为高。如果两个查询束具有值为 0 的优先级，并且没有足够的资源同时运行两个查询，则会计划其中一个查询。一秒钟之后，未计划查询的优先级的值将为 100，并抢占已计划的查询。又过两秒钟之后，被抢占查询的优先级值当前为 200，并且两个查询再次交换位置。两个查询都未完成，因为每隔两秒钟，当前正在计算的查询即会被抢占，以便另一个查询可以运行。） </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Daily Schedule Policy（每日计划策略） </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>让您在每天的指定时间更改优先级。此计划对于自动客户端（例如<span class="wintitle">报表服务器</span>）和住在不同时区的系统用户特别有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更改 </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>右键单击可添加计划的优先级更改。Change Time（更改时间）是更改发生时的时间。格式为 hour:minutes AM/PM。如果未输入 AM 或 PM，则系统使用军用标准时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Priority Limit（优先级限制） </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>因更改产生的最大优先级值。Priority Change（优先级更改）是优先级中添加的量。例如，值 0 返回到默认的优先级。任何其他值都会产生一个由默认优先级加上此数值而得到的优先级。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Users（用户） </p> </td> 
   <td colname="col2"> <p>矢量 </p> </td> 
   <td colname="col3"> <p>列出身为组成员的用户。 </p> <p> <b>Name（名称）：</b>在用户证书的“通用名称”字段中显示的用户名称。 </p> <p> <b>Extra Priority（额外优先级）：</b>向用户组的基本优先级提供额外的优先级以确定该用户的起始优先级。 </p> </td> 
  </tr> 
 </tbody> 
</table>

