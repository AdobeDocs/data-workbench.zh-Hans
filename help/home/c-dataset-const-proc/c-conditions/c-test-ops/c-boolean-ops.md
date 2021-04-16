---
description: 布尔运算合并测试运算的结果，测试运算用作布尔运算的子项。
title: 布尔运算
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 12%

---

# 布尔运算{#boolean-operations}

布尔运算合并测试运算的结果，测试运算用作布尔运算的子项。

有关测试操作的信息，请参阅[测试操作](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144)。 定义[!DNL boolean]操作时，可以为该操作定义零个或多个子项。

**向布尔运算中添加子条件**

1. 右键单击与[!DNL Boolean]操作对应的名称或编号。
1. 单击&#x200B;**[!UICONTROL Add new child]**&#x200B;并选择要添加的可用条件类型之一。
1. 重复步骤1和2，直到您为[!DNL Boolean]操作添加了所有所需的子条件。

   >[!NOTE]
   >
   >右键单击与[!DNL Boolean]操作对应的名称或编号时，将显示[!DNL Add new sibling]菜单选项。 同级是条件层次结构中与右键单击的[!DNL Boolean]操作处于相同相对位置的另一个条件。 为[!DNL Boolean]操作添加新同级与通过右键单击[!DNL Condition]或[!DNL Log Entry Condition]参数添加新条件相同。

**从布尔运算中删除子条件：**

1. 右键单击要从[!DNL Boolean]操作中删除的子条件的名称或与子条件对应的编号。
1. 单击&#x200B;**[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>，其中number是与要删除的子条件对应的数字。

本节讨论以下条件：

* [和](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [都不](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [或](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## 和  {#section-a14dba4b07cc4ab9aeb20868f773db7c}

[!DNL And]条件可以具有零个或多个子条件，并且当其子节点中没有一个返回false时返回true。

[!DNL And]条件构成Data Workbench Server内所有条件测试的根操作。 如果[!DNL And]条件不包含子项，则该条件的计算结果为true，并且相关操作继续进行。 这就是为什么只有[!DNL And]条件作为条件测试的操作始终执行，以及它被用作所有条件测试的根的原因。

此示例说明如何使用[!DNL And]条件确保在2006年仅日志条目日期发生且请求的页面为[!DNL /products/purchase.asp]时发生[!DNL Copy]转换。

![](assets/cfg_Condition_AndCondition.png)

## 都不 {#section-7e48b61266aa43ecbc48b979bf5e939b}

[!DNL Neither]条件可以具有零个或多个子条件，如果其任何子条件的计算结果为true，则返回false。 如果[!DNL Neither]条件不包含子项，则其子项都不能返回true。 结果，[!DNL Neither]条件的计算结果为true。

以下示例显示了一个[!DNL Neither]条件，其子项为两个[!DNL Range]条件。 如所定义，[!DNL Neither]条件不包括2007年1月1日至2007年1月10日之间或2007年1月12日至2007年1月14日期间发生的日志条目。 此类条件可用作[!DNL Log Entry Condition]以在收集数据存在已知问题的期间从数据集中消除事务。

![](assets/cfg_Condition_NeitherCondition.png)

## 或 {#section-a3aa0f56b6234f2680fa81939228326b}

[!DNL Or]条件可以具有零个或多个子条件，并且如果其至少一个子条件的计算结果为true，则返回true。 如果[!DNL Or]条件不包含子项，则其子项都不能返回true。 结果，[!DNL Or]条件的计算结果为false。

此示例显示[!DNL Or]条件，其子项为[!DNL String Match]条件和[!DNL Range]条件。 仅当日志条目的[!DNL x-hasproblem]值设置为yes或日志条目在2007年1月1日到2007年1月10日的时间范围内发生时，才满足[!DNL Or]条件。

![](assets/cfg_Condition_OrCondition.png)
