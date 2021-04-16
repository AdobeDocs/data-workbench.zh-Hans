---
description: 服务器监视器界面对于诊断或仅跟踪作为Data Workbench服务器计算机客户端的Data Workbench服务器计算机和报告计算机的性能参数很有用。
title: 服务器监视器界面
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 63%

---

# 服务器监视器界面{#server-monitor-interface}

服务器监视器界面对于诊断或仅跟踪作为Data Workbench服务器计算机客户端的Data Workbench服务器计算机和报告计算机的性能参数很有用。

服务器监视器界面在计算机名称的左侧顶部显示一个绿色圆点或红色圆点。绿色圆点指示计算机工作正常，没有任何问题。红色节点指示计算机上出现了一个或多个错误。

服务器监视器界面比较靠下的部分列出了每个可用配置文件的处理状态，以及有关该计算机的性能详细信息。

有关[!DNL Data Workbench servers]的详细信息，请参阅&#x200B;*《服务器产品安装和管理指南》*。 有关[!DNL Report]的详细信息，请参阅&#x200B;*Data Workbench报告指南*。

**打开服务器监视器界面**

* 在“服务器管理器”中，右键单击Data Workbench服务器或[!DNL Report]计算机的节点。 t

单击&#x200B;**[!UICONTROL Server Monitor]**&#x200B;可视图有关一台服务器的详细信息，或单击&#x200B;**[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]**&#x200B;可视图有关相关服务器群集的详细信息。

![](assets/vis_ServerMonitor.png)

[!DNL Server Monitor]接口每10秒自动更新一次。

下表列表了可使用[!DNL Server Monitor]接口完成的任务。

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 若要执行此任务... </th> 
   <th colname="col2" class="entry"> 执行此操作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>检查配置文件的日志处理状态 </p> </td> 
   <td colname="col2"> <p>查看 Profile <i>配置文件名称</i>矢量。在以上示例中，通过查看 Profile ExampleProfile（配置文件 ExampleProfile）矢量，可以看到 ExampleProfile 配置文件在一个服务器上处理，并且其日志处理已 100% 完成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>确定计算机响应请求所用的时间 </p> </td> 
   <td colname="col2"> <p>查看轮询延迟字段。如果该值大于 1000 毫秒，请联系 Adobe 支持服务部门。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看完成转换和查询大致所用的时间 </p> </td> 
   <td colname="col2"> <p>查看扫描时间 (hh:mm:ss) 字段，它仅在转换或查询过程中出现。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>确定计算机的当前网络连接数 </p> </td> 
   <td colname="col2"> <p>查看计算机的<span class="wintitle">服务器监视器</span>信息的最后一行。在以上示例中，您看到有 2 个网络连接当前来自一台计算机。 </p> </td> 
  </tr> 
 </tbody> 
</table>
