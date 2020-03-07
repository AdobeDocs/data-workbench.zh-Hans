---
description: 通常，Data Workbench Server在收到传入的用户查询时会进行回答，并继续提供结果和实时更新，直到用户不再请求这些查询。
solution: Analytics
title: 查询队列
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查询队列{#query-queue}

通常，Data Workbench Server在收到传入的用户查询时会进行回答，并继续提供结果和实时更新，直到用户不再请求这些查询。

有时，尤其是在具有许多Data Workbench用户的系统上，活动查询的数量比从服务器获得的系统资源要多。 [!DNL Query Queue] 允许服务器暂时暂停某些查询，直到提供答案所需的资源可用为止。 The [!DNL Query Queue] also provides features to prioritize queries based on a variety of parameters, so that in case of resource contention, higher-priority queries are answered first.

来自单个客户端或报表服务器的查询被放置在一个束中，并作为一个整体计划时间。您可以配置资源监视器以限制查询所使用的特定系统资源量。当监视的资源允许计划另一个查询束时，将计划具有最高优先级的束。由于资源限制，尚未计划查询的用户不会收到错误，但是会被告知他们的查询已置于队列中，并且用户可以继续使用本地采样。

The default configuration includes a simple configuration for the [!DNL Query Queue], but leaves it disabled. Administrators can enable or disable the [!DNL Query Queue], configure resource monitors to determine how much of various resources are used for querying, and configure complex prioritization policies for different users.

**为[!DNL Query Queuing]**

1. 通过 [!DNL Server.cfg] 单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** >打开 **[!UICONTROL Dataset]**。
1. 右键单击 **[!UICONTROL Server.cfg]** 并制作本地副本以进行编辑。
1. 展开 [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. 配置以下参数：

   * **User Groups（用户组）：**&#x200B;可让您配置策略、用户和队列优先级。请参阅[查询队列用户组](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)以了解定义。

   * **活动：** （矢量）启用或禁用 [!DNL Query Queue]。 有效值为 true 或 false。默认值设置为 false。

   * **Default User Group（默认用户组）：**（字符串）在用户未在任何用户组中列出的情况下，键入将这些用户添加到的用户组的名称。
   * **Resource Monitors（资源监视器）：**（矢量）右键单击可添加资源监视器。You can specify whether the [!DNL Query Queue] monitors memory or the number of queries. 右键单击 **[!UICONTROL Resource Monitor]**（资源监视器）可选择内存预算监视器或查询数量监视器。See [Query Queue Resource Monitors](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) for more information.

   * **Untouchable Priority（不容更改的优先级）：**（整数）指定优先级大于或等于该值的束永远不会被计划为更高优先级的束抢占。与用户组参数表 [!DNL Memory Budget Monitor] 中所述的一 [起使用](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)。

