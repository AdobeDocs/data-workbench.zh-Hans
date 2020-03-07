---
description: 在实施Data Workbench时收集并描述适合您的营销环境的业务问题。
title: Data Workbench发现和要求
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Data Workbench发现和要求{#data-workbench-discovery-and-requirements}

在实施Data Workbench时收集并描述适合您的营销环境的业务问题。

本节允许您收集有关在Data Workbench(DWB)中设计解决方案所需问题和任务的输入，这些问题和任务可以准确、明确、技术独立地解决，并提供对业务术语和Adobe Analytics Premium解决方案的参考。 本节提供有关这些目标和相关要求的信息。

## 阶段1:主要业务目标／目标 {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

下表提示您确定客户群并分析DWB实施的构建。

* 了解您的客户群
* 了解特定业务案例（例如，自助服务和其他数据渠道／线下数据源的有效性）

**了解您的客户基础**

了解客户为何使用您的网站、您面临的挑战，以及DWB如何根据您的业务模式帮助您。 例如，如何衡量、监控和分析客户以交叉销售其他产品和服务，获取活跃用户和帐户渗透率的列表以及其他目标。

| ID | 业务问题／要求 | 优先级 | 阶段 | 依赖关系 |
|---|---|---|---|---|
| 1a | 特定业务问题1 | 高／中/低 | 1 | 公用密钥，取决于其他一些密钥等。 |
| 1b | 特定业务问题2 | 高 | 1 | 任何依赖关系 |

分析构建

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">工作区分析数据源</td> 
   <td colname="col2"> 添加工作区名称 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>需要的工作区维度和指标 </p> </td> 
   <td colname="col2"> <p>识别维度： </p> <p>识别指标： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 需要的工作区过滤器、标记和工具 </td> 
   <td colname="col2"> <p>识别细分： </p> <p>识别工具： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可以从此分析中得出哪些操作？ </td> 
   <td colname="col2"> 使用特定的DWB工作区了解任务和内容。 </td> 
  </tr> 
 </tbody> 
</table>

## 阶段2:了解特定业务案例 {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

了解其他数据源和渠道，并了解这些数据源和渠道与您的业务案例有何关系。

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 业务问题／要求 </th> 
   <th colname="col3" class="entry"> 优先级 </th> 
   <th colname="col04" class="entry"> 阶段 </th> 
   <th colname="col4" class="entry"> 依赖关系 </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> 特定业务要求1 </td> 
   <td colname="col3"> <p>高／中/低 </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>公用密钥，取决于其他一些密钥、帐户标志／标识符等。 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>特定业务要求2 </p> </td> 
   <td colname="col3"> 高／中/低 </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>任何依赖关系 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**分析构建**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">工作区分析数据源
     </td> 
   <td colname="col2">
     工作区名称示例 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>需要的工作区维度和指标 </p> </td> 
   <td colname="col2"> <p>维：定义所需的维。 </p> <p>指标：定义所需的指标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 需要的工作区过滤器、标记和工具 </td> 
   <td colname="col2"> <p>区段：识别客户细分。 </p> <p>工具：选择所需的工具。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可以从此分析中得出哪些操作？ </td> 
   <td colname="col2"> 从此工作区了解什么 </td> 
  </tr> 
 </tbody> 
</table>

**数据源**

| 数据源 | 优先级 | 数据的接收频率是多少？ |
|---|---|---|
| 站点1名称报告套件(RSID) | 1 | 每小时 |
| 站点2名称（如果有）(RSID) | 1 | 每小时 |
| 数据源1（如果适用） | 2 | 每日? |
| 数据源2（如果适用） | 3 | 每日? |
