---
description: 在工作区中，可视化表示一组查询结果。
solution: Analytics
title: 了解选择如何影响其他可视化
topic: Data workbench
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解选择如何影响其他可视化{#understanding-how-a-selection-affects-other-visualizations}

在工作区中，可视化表示一组查询结果。

进行选择时，Data Workbench会过滤查询的结果，查询结果用于在工作区中生成可视化。 具体的过滤器因可视化而异。

以下示例说明了Data Workbench如何将选择应用到三种不同类型的可视化。 查看这些示例可帮助您了解选择对可视化的过滤影响，同时还帮助您了解如何解释您在过滤的可视化中看到的结果。

* [用“会话数”量度过滤可视化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [用“访客数”量度过滤可视化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [用“基于会话的访客数”量度过滤可视化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## 用“会话数”量度过滤可视化 {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

In this example, the [!DNL /direct.asp/?ldPage=hme] URI in the visualization on the left is filtering the metric for Sessions displayed in the visualization on the right.

![](assets/client-vis1.png)

* **选择对查询的影响：** Data Workbench会过滤选定URI的“会话”。 In this example, the query that generates the value for the [!DNL /pops/disclosure_pop.asp] element is filtered as follows:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **解释可视化：** 筛选的可视化表示包含在可视化和中列出的URI的会话数 [!DNL /direct.asp/?ldPage=hme]。 This example shows that there were 1,113 sessions during which visitors viewed both [!DNL /pops/disclosure_pop.asp] page and [!DNL /direct.asp/?ldPage=hme] in the same session.

## 用“访客数”量度过滤可视化 {#section-97d38c7f03e8457189a9c72d69514ed2}

In this example, the [!DNL /direct.asp/?ldPage=home] URI in the visualization on the left is filtering the metric for Visitors in the visualization on the right.

![](assets/client-vis2.png)

* **选择对查询的影响：** Data Workbench会过滤选定URI的“访客”。 In this example, the query that generates the value for the [!DNL /pops/disclosure_pop.asp] URI is filtered as follows:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **解释可视化：** 筛选的可视化描述了已查看可视化中列出的URI的访 [!DNL /direct.asp/?ldPage=hme] 客（尽管不一定在同一会话中）。 The example above shows that 2,041 visitors have viewed both [!DNL /pops/disclosure_pop.asp] and [!DNL /direct.asp/?ldPage=hme].

## 用“基于会话的访客数”量度过滤可视化 {#section-f746182311d648dcb98716b0fe846e25}

In this example, the [!DNL /direct.asp/?ldPage=hme] URI in the visualization on the left is filtering the metric for visitor-by-session in the visualization on the right.

![](assets/client-vis3.png)

* **选择对查询的影响：** Data Workbench会为选定的URI按会话筛选访客。 For example, the query that generates the value for the [!DNL /pops/disclosure_pop.asp] URI is filtered as follows:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **解释可视化：** 过滤后的可视化描述了在可视化中和同一会话中同时查看了URI [!DNL /direct.asp/?ldPage=hme] 的访客。 This example shows that 1,069 visitors saw both [!DNL /pops/disclosure_pop.asp] and [!DNL /direct.asp/?ldPage=hme] during a single session.

