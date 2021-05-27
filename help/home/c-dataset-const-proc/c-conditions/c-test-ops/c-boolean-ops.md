---
description: 布尔运算合并测试运算的结果，测试运算用作布尔运算的子项。
title: 布尔运算
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 12%

---

# 布尔运算{#boolean-operations}

布尔运算合并测试运算的结果，测试运算用作布尔运算的子项。

有关测试操作的信息，请参阅[测试操作](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144)。 定义[!DNL boolean]操作时，可以为该操作定义零个或多个子项。

**向布尔运算中添加子条件**

1. 右键单击[!DNL Boolean]操作对应的名称或编号。
1. 单击&#x200B;**[!UICONTROL Add new child]**，然后选择要添加的可用条件类型之一。
1. 重复步骤1和2，直到为[!DNL Boolean]操作添加所有所需的子条件。

   >[!NOTE]
   >
   >右键单击与[!DNL Boolean]操作对应的名称或编号时，会看到[!DNL Add new sibling]菜单选项。 同级是条件层次结构中与右键单击的[!DNL Boolean]操作处于相同相对位置的另一个条件。 为[!DNL Boolean]操作添加新同级项与通过右键单击[!DNL Condition]或[!DNL Log Entry Condition]参数添加新条件相同。

**从布尔运算中删除子条件：**

1. 右键单击要从[!DNL Boolean]操作中删除的子条件的名称或与该子条件对应的编号。
1. 单击&#x200B;**[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>，其中number是与要删除的子条件对应的数字。

本节讨论以下条件：

* [和](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [都不](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [或](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## “逻辑与”{#section-a14dba4b07cc4ab9aeb20868f773db7c}

[!DNL And]条件可以具有零个或多个子条件，并且当其子节点没有返回false时，该条件会返回true。

[!DNL And]条件构成Data Workbench Server中所有条件测试的根运算。 如果[!DNL And]条件不包含子项，则该条件的计算结果为true，并继续相关运算。 这就是仅将[!DNL And]条件作为条件测试的操作始终执行的原因，以及将其用作所有条件测试的根的原因。

此示例显示如何使用[!DNL And]条件确保在2006年仅发生日志条目日期且请求的页面为[!DNL /products/purchase.asp]时才发生[!DNL Copy]转换。

![](assets/cfg_Condition_AndCondition.png)

## 都不 {#section-7e48b61266aa43ecbc48b979bf5e939b}

[!DNL Neither]条件可以具有零个或多个子条件，如果其任何子条件的计算结果为true，则返回false。 如果[!DNL Neither]条件不包含子条件，则其子条件均不能返回true。 因此，[!DNL Neither]条件的计算结果为true。

以下示例显示了一个[!DNL Neither]条件，其子条件为两个[!DNL Range]条件。 根据定义，[!DNL Neither]条件不包括2007年1月1日至2007年1月10日期间或2007年1月12日至2007年1月14日期间发生的日志条目。 此类条件可用作[!DNL Log Entry Condition]，以在收集的数据存在已知问题期间从数据集中排除事务。

![](assets/cfg_Condition_NeitherCondition.png)

## 或 {#section-a3aa0f56b6234f2680fa81939228326b}

[!DNL Or]条件可以具有零个或多个子条件，如果其子条件中的至少一个计算结果为true，则返回true。 如果[!DNL Or]条件不包含子条件，则其子条件均不能返回true。 因此，[!DNL Or]条件的计算结果为false。

此示例显示了以[!DNL String Match]条件和[!DNL Range]条件作为子条件的[!DNL Or]条件。 仅当日志条目的[!DNL x-hasproblem]值设置为“是”或日志条目在2007年1月1日到2007年1月10日的时间范围内发生时，才满足[!DNL Or]条件。

![](assets/cfg_Condition_OrCondition.png)
