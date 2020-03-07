---
description: 新访客条件是一种与网站数据一起使用的条件运算，用于确定要考虑将哪些访客加入数据集中。
solution: Analytics
title: 新访客条件
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 新访客条件{#new-visitor-condition}

新访客条件是一种与网站数据一起使用的条件运算，用于确定要考虑将哪些访客加入数据集中。

The [!DNL New Visitor Condition] defines the first log entry (ordered by time) for a visitor that is to be used in the dataset, and all subsequent log entries for this visitor are included in the dataset regardless of whether they meet this condition. Because the [!DNL New Visitor Condition] requires that data is ordered by visitor and time, it is applied only during the transformation phase of dataset construction.

The [!DNL New Visitor Condition] shown in this example creates a dataset that includes only those log entries for visitors who respond to email campaigns. 这通过使用 [!DNL NotEmptyCondition] 测试（请参阅[不为空](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)）并将 [!DNL x-campaign-email] 字段用作正则表达式的输入来完成。在识别符合条件的新访客之后，系统会捕获这些访客的所有日志条目。

![](assets/cfg_Transformation_NewVisitorCondition.png)

