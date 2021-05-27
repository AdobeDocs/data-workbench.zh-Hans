---
description: 转换和维度使用条件确定某些指令或操作应用于日志字段的时间。
title: 关于条件
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 51%

---

# 关于条件{#about-conditions}

转换和维度使用条件确定某些指令或操作应用于日志字段的时间。

Log Entry Condition（日志条目条件）参数使用条件确定在数据集构建过程中应包含哪些日志条目。本附录介绍了 Data Workbench Server 内可用的各类条件。

条件分为以下两种类别：

* **[!DNL Test Operations]:** [!DNL Compare]、 [!DNL Not Empty]、 [!DNL Range]、 [!DNL Regular Expression]和条 [!DNL String Match] 件用于测试可用日志字段中的不同状态。

* **[!DNL Boolean Operations]:** 使用 [!DNL And]、 [!DNL Or]和 [!DNL Neither] 条件来组合上述测试运算。例如，如果您有[!DNL Range]条件和[!DNL String Match]条件，这两个条件必须均为false才能采取相应的操作，则应将这两个运算设为[!DNL Neither]条件的子项。 请注意，[!DNL And]条件用作系统中所有条件测试的根。
