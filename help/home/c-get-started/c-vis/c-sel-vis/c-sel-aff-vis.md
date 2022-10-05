---
description: 在工作区中，可视化表示一组查询结果。
title: 了解选择如何影响其他可视化图表
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 26%

---

# 了解选择如何影响其他可视化图表{#understanding-how-a-selection-affects-other-visualizations}

{{eol}}

在工作区中，可视化表示一组查询结果。

进行选择时，Data Workbench会过滤查询的结果，以在工作区中生成可视化。 具体的过滤器因可视化而异。

以下示例说明了Data Workbench如何将一个选择应用于三种不同类型的可视化。 查看这些示例可帮助您了解选择对可视化的过滤影响，同时还帮助您了解如何解释您在过滤的可视化中看到的结果。

* [用“会话数”量度过滤可视化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [用“访客数”量度过滤可视化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [用“基于会话的访客数”量度过滤可视化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## 用“会话数”量度过滤可视化 {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

在本例中， [!DNL /direct.asp/?ldPage=hme] 左侧可视化中的URI用于过滤右侧可视化中显示的会话数量度。

![](assets/client-vis1.png)

* **选择对查询的影响：** Data Workbench过滤选定URI的会话。 在本例中，用于为 [!DNL /pops/disclosure_pop.asp] 元素的过滤方式如下：

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **解释可视化：** 过滤的可视化表示包含可视化和 [!DNL /direct.asp/?ldPage=hme]. 此示例显示，在1,113个会话中，访客同时查看了这两个会话 [!DNL /pops/disclosure_pop.asp] 页面和 [!DNL /direct.asp/?ldPage=hme] 在同一会话中。

## 用“访客数”量度过滤可视化 {#section-97d38c7f03e8457189a9c72d69514ed2}

在本例中， [!DNL /direct.asp/?ldPage=home] 左侧可视化中的URI用于过滤右侧可视化中的访客量度。

![](assets/client-vis2.png)

* **选择对查询的影响：** Data Workbench过滤选定URI的访客。 在本例中，用于为 [!DNL /pops/disclosure_pop.asp] URI的过滤方式如下：

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **解释可视化：** 过滤的可视化描述了已查看可视化和 [!DNL /direct.asp/?ldPage=hme] （尽管不一定在同一会话期间）。 上例显示2,041位访客同时查看了这两项内容 [!DNL /pops/disclosure_pop.asp] 和 [!DNL /direct.asp/?ldPage=hme].

## 用“基于会话的访客数”量度过滤可视化 {#section-f746182311d648dcb98716b0fe846e25}

在本例中， [!DNL /direct.asp/?ldPage=hme] 左侧可视化中的URI用于过滤右侧可视化中的按会话访客量度。

![](assets/client-vis3.png)

* **选择对查询的影响：** Data Workbench按会话过滤选定URI的访客。 例如，为 [!DNL /pops/disclosure_pop.asp] URI的过滤方式如下：

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **解释可视化：** 过滤的可视化描述了查看了可视化和 [!DNL /direct.asp/?ldPage=hme] 在同一会话期间。 此示例显示，1,069位访客同时查看了这两项 [!DNL /pops/disclosure_pop.asp] 和 [!DNL /direct.asp/?ldPage=hme] 在单个会话期间。
