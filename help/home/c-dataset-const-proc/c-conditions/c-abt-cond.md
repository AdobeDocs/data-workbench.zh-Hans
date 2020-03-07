---
description: 转换和维度使用条件确定某些指令或操作应用于日志字段的时间。
solution: Analytics
title: 关于条件
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 关于条件{#about-conditions}

转换和维度使用条件确定某些指令或操作应用于日志字段的时间。

Log Entry Condition（日志条目条件）参数使用条件确定在数据集构建过程中应包含哪些日志条目。本附录介绍了 Data Workbench Server 内可用的各类条件。

条件分为以下两种类别：

* **[!DNL Test Operations]:**[!DNL Compare]、、[!DNL Not Empty]、和[!DNL Range][!DNL Regular Expression][!DNL String Match]条件用于测试可用日志字段中的不同状态。

* **[!DNL Boolean Operations]:**使[!DNL And]用[!DNL Or]、和[!DNL Neither]条件组合上述测试操作。 For example, if you have a[!DNL Range]condition and a[!DNL String Match]condition that must both be false to take the appropriate action, you would make these two operations children of the[!DNL Neither]condition. Note that the[!DNL And]condition is used as the root of all condition testing in the system.

