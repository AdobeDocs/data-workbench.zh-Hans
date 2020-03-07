---
description: 布尔运算合并测试运算的结果，测试运算用作布尔运算的子项。
solution: Analytics
title: 布尔运算
topic: Data workbench
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 布尔运算{#boolean-operations}

布尔运算合并测试运算的结果，测试运算用作布尔运算的子项。

For information about the test operations, see [Test Operations](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). When you define a [!DNL boolean] operation, you can define zero or more children for the operation.

**向布尔运算中添加子条件**

1. Right-click the name or the number corresponding to the [!DNL Boolean] operation.
1. Click **[!UICONTROL Add new child]** and choose one of the available condition types to add.
1. Repeat steps 1 and 2 until you have added all of the desired child conditions for the [!DNL Boolean] operation.

   >[!NOTE]
   >
   >When you right-click the name or the number corresponding to a [!DNL Boolean] operation, you see the [!DNL Add new sibling] menu option. A sibling is another condition at the same relative position in the condition hierarchy as the [!DNL Boolean] operation that you right-clicked. Adding a new sibling for a [!DNL Boolean] operation is the same as adding a new condition by right-clicking the [!DNL Condition] or [!DNL Log Entry Condition] parameter.

**从布尔运算中删除子条件：**

1. Right-click the name of the child condition or the number corresponding to the child condition that you want to remove from the [!DNL Boolean] operation.
1. Click **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, where number is the number corresponding to the child condition that you want to remove.

本节将讨论以下条件：

* [和](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [都不](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [或](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## 和 {#section-a14dba4b07cc4ab9aeb20868f773db7c}

The [!DNL And] condition can have zero or more child conditions and returns true when none of its children nodes return false.

The [!DNL And] condition forms the root operation of all condition testing within the data workbench server. If the [!DNL And] condition contains no children, the condition evaluates to true and the associated operation proceeds. This is why actions that have only the [!DNL And] condition as the condition test always execute and why it is used as the root for all condition tests.

This example shows how an [!DNL And] condition is used to make sure that the [!DNL Copy] transformation occurs when only both the date of the log entry occurred in the year 2006 and that the page requested was [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## 都不 {#section-7e48b61266aa43ecbc48b979bf5e939b}

The [!DNL Neither] condition can have zero or more child conditions and returns false if any of its child conditions evaluate to true. If the [!DNL Neither] condition contains no children, none of its children can return true. As a result, the [!DNL Neither] condition evaluates to true.

The following example shows a [!DNL Neither] condition with two [!DNL Range] conditions as its children. 如所定义，该条 [!DNL Neither] 件不包括在2007年1月1日至2007年1月10日之间或在2007年1月12日至2007年1月14日期间发生的日志条目。 在已知数据收集有问题的时 [!DNL Log Entry Condition] 间段内，这种条件可用作消除数据集中的事务。

![](assets/cfg_Condition_NeitherCondition.png)

## 或 {#section-a3aa0f56b6234f2680fa81939228326b}

The [!DNL Or] condition can have zero or more child conditions and returns true if at least one of its child conditions evaluate to true. If the [!DNL Or] condition contains no children, none of its children can return true. As a result, the [!DNL Or] condition evaluates to false.

This example shows the [!DNL Or] condition with a [!DNL String Match] condition and a [!DNL Range] condition as its children. The [!DNL Or] condition is satisfied only if the log entry has the [!DNL x-hasproblem] value set to yes or the log entry occurred during the time range January 1, 2007, to January 10, 2007.

![](assets/cfg_Condition_OrCondition.png)

