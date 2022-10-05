---
description: 可以使用工作表来指示量度已达到定义的阈值。
title: 创建量度指标
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
exl-id: 5713f3dd-85ef-407c-b21c-80e9b4390b6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 62%

---

# 创建量度指标{#create-a-metric-indicator}

{{eol}}

可以使用工作表来指示量度已达到定义的阈值。

此外，您还可以使用 [!DNL Report] 当量度在指定时间范围内达到定义的阈值时自动生成和分发报表。

有关 [!DNL Report]，请参阅 *Data Workbench报表指南*.

* [向上箭头或向下箭头指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [检查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**使用工作表创建量度指示器**

1. 定义工作表单元格的内容。

   1. 在A列中，输入所需量度的名称(例如， [!DNL Visitors])。
   1. 在B列中，输入所需量度的值(例如， [!DNL =Visitors])。
   1. 在 C 列中，输入该量度的低阈值。
   1. 在 D 列中，输入该量度的高阈值。
   1. 在 E 列中，输入适当的公式。有关示例，请参阅[向上箭头或向下箭头指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)或[检查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)。
   1. 在公式单元格（E列）中，右键单击并单击 **[!UICONTROL Format]** > **[!UICONTROL Indicator]**，然后单击以下任一项：

      * **[!UICONTROL None]**:列出确切的计算方式，而不是指示器。
      * **[!UICONTROL Check]**:使用复选标记或X指示该值高于或低于您设置的阈值，具体取决于您的公式。 请参阅[检查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)。
      * **[!UICONTROL Up or Down]**:使用向上或向下箭头指示值是低于低阈值（向下箭头）、高阈值（向上箭头），还是介于低阈值和高阈值（空白）之间。 请参阅[向上箭头或向下箭头指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)。

1. 对要为其创建指示器的其他量度重复步骤 1。

所得到的工作表将如以下示例所示：

![](assets/vis_Worksheet_Alerts.png)

## 向上或向下指示器 {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

对于 [!DNL Up] 或 [!DNL Down indicator]，请使用以下公式：

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

例如：[!DNL =(b2-c2)/(d2-c2)*2-1]

将此公式与 [!DNL Up] 或 [!DNL Down indicator]:

* 如果量度值介于低阈值和高阈值之间，则公式的计算结果为介于 -1 和 1 之间的一个数字（不包括 -1 和 1）。向上箭头或向下箭头不在工作表中显示。
* 如果量度值小于或等于低阈值，则公式的计算结果为小于或等于 -1 的值。量度指示器更改为向下箭头。
* 如果量度值大于或等于高阈值，则公式的计算结果为大于或等于 1 的数字。量度指示器更改为向上箭头。

以下工作表说明了示例公式 [!DNL =(b2-c2)/(d2-c2)*2-1] 将显示：

![](assets/vis_Worksheet_Alerts_UpDown.png)

## 检查指示器 {#section-98c5298a74f34dcbaaf151549fcc7090}

对于 [!DNL Check indicator]，则使用公式来指示当量度值高于或低于您指定的阈值时，是否要通知您。 例如：

* 如果您希望在该值低于您设置的阈值时通知您，则可以使用以下格式：

   * [!DNL threshold - metric]

      例如：[!DNL =(c2-b2)]

* 如果您希望在该值高于您设置的阈值时通知您，则可以使用以下公式：

   * [!DNL metric - threshold]

      例如：[!DNL =(b3-c3)]

当显示复选标记时，该公式的计算结果为正数。当显示 X 时，该公式的计算结果为负数。

使用 [!DNL Check indicator]:

* 如果公式指示保持量度值高于阈值是比较理想的，则当量度值大于或等于阈值时显示复选标记，当该值小于阈值时显示 X。
* 如果公式指示保持量度值低于阈值是比较理想的，则当量度值小于或等于阈值时显示复选标记，当该值大于阈值时显示 X。

以下工作表说明了示例公式 [!DNL =(c2-b2)] 和 [!DNL =(b3-c3)] 将显示：

![](assets/vis_Worksheet_Alerts_Check.png)
