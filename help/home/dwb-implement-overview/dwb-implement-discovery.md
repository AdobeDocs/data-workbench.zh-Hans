---
description: 在实施Data Workbench时，收集并描述与您的营销环境相适应的业务问题。
title: Data Workbench 探索与要求
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
exl-id: 25cc2940-800a-4ad2-a7bb-c343e3d65500
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 8%

---

# Data Workbench 探索与要求{#data-workbench-discovery-and-requirements}

{{eol}}

在实施Data Workbench时，收集并描述与您的营销环境相适应的业务问题。

利用此部分，可收集有关在Data Workbench(DWB)中设计解决方案所需的问题和任务的投入，该解决方案可以准确、明确地以独立于技术的方式解决这些问题，并提供业务术语和Adobe Analytics Premium解决方案的参考。 本节提供有关这些目标和相关要求的信息。

## 阶段1:主要业务目标/目标 {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

下表提示您识别客户群并分析DWB实施的构建。

* 了解您的客户群
* 了解特定业务案例（例如，自助服务和其他数据渠道/离线数据源的有效性）

**了解您的客户群**

了解客户为何使用您的网站、您面临的挑战，以及DWB如何根据您的业务模型来帮助您。 例如，如何测量、监控和分析客户，以交叉销售其他产品和服务，获取活跃用户和客户渗透率的列表，以及其他目标。

| ID | 业务问题/要求 | 优先级 | 阶段 | 依赖关系 |
|---|---|---|---|---|
| 1a | 特定业务问题1 | 高/中/低 | 1 | 公共键，取决于其他键等。 |
| 1b | 具体业务问题2 | 高 | 1 | 任何依赖项 |

分析结构

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">工作区分析数据源</td> 
   <td colname="col2"> 添加工作区名称 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>所需的工作区Dimension和量度 </p> </td> 
   <td colname="col2"> <p>识别Dimension: </p> <p>识别量度： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 所需的工作区过滤器、标记和工具 </td> 
   <td colname="col2"> <p>识别区段： </p> <p>识别工具： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可以从此分析中派生哪些操作？ </td> 
   <td colname="col2"> 使用特定的DWB工作区了解任务和内容。 </td> 
  </tr> 
 </tbody> 
</table>

## 阶段2:了解特定业务案例 {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

了解其他数据源和渠道，并了解这些数据源和渠道与您的业务案例有何关联。

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 业务问题/要求 </th> 
   <th colname="col3" class="entry"> 优先级 </th> 
   <th colname="col04" class="entry"> 阶段 </th> 
   <th colname="col4" class="entry"> 依赖关系 </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> 具体业务要求1 </td> 
   <td colname="col3"> <p>高/中/低 </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>公用密钥，取决于其他一些密钥、帐户标记/标识符等。 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>具体业务要求2 </p> </td> 
   <td colname="col3"> 高/中/低 </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>任何依赖项 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**分析结构**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">工作区分析数据源
     </td> 
   <td colname="col2">
     工作区名称示例 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>所需的工作区Dimension和量度 </p> </td> 
   <td colname="col2"> <p>Dimension:定义所需的维度。 </p> <p>量度：定义所需的量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 所需的工作区过滤器、标记和工具 </td> 
   <td colname="col2"> <p>区段：确定客户区段。 </p> <p>工具：选择所需的工具。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可以从此分析中派生哪些操作？ </td> 
   <td colname="col2"> 从此工作区了解什么 </td> 
  </tr> 
 </tbody> 
</table>

**数据源**

| 数据源 | 优先级 | 多久收到一次数据？ |
|---|---|---|
| 网站1名称报表包(RSID) | 1 | 每小时 |
| 站点2名称（如果有）(RSID) | 1 | 每小时 |
| 数据源1（如果适用） | 2 | 每日? |
| 数据源2（如果适用） | 3 | 每日? |
