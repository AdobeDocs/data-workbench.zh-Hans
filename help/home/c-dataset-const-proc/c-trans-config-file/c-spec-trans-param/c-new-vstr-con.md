---
description: 新访客条件是一种与网站数据一起使用的条件运算，用于确定要考虑将哪些访客加入数据集中。
title: 新访客条件
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 52%

---

# 新访客条件{#new-visitor-condition}

新访客条件是一种与网站数据一起使用的条件运算，用于确定要考虑将哪些访客加入数据集中。

[!DNL New Visitor Condition]定义要在数据集中使用的访客的第一个日志条目（按时间排序），此访客的所有后续日志条目都包含在数据集中，而不管这些条目是否满足此条件。 由于[!DNL New Visitor Condition]要求数据按访客和时间排序，因此它仅在数据集构建的转换阶段应用。

此示例中显示的[!DNL New Visitor Condition]创建的数据集仅包括响应电子邮件活动的访客的日志条目。 这通过使用 [!DNL NotEmptyCondition] 测试（请参阅[不为空](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)）并将 [!DNL x-campaign-email] 字段用作正则表达式的输入来完成。在识别符合条件的新访客之后，系统会捕获这些访客的所有日志条目。

![](assets/cfg_Transformation_NewVisitorCondition.png)
