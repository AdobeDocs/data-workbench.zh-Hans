---
description: 可以使用工作表来指示量度已达到定义的阈值。
solution: Analytics
title: 创建度量指示符
topic: Data workbench
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 创建度量指示符{#create-a-metric-indicator}

可以使用工作表来指示量度已达到定义的阈值。

In addition, you can use [!DNL Report] to automatically generate and distribute a report when a metric reaches a defined threshold within a specified time frame.

For more information about [!DNL Report], see the *Data Workbench Report Guide*.

* [向上箭头或向下箭头指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [检查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**使用工作表创建量度指示器**

1. 定义工作表单元格的内容。

   1. In Column A, enter the name of the desired metric (for example, [!DNL Visitors]).
   1. In Column B, enter the value of the desired metric (for example, [!DNL =Visitors]).
   1. 在 C 列中，输入该量度的低阈值。
   1. 在 D 列中，输入该量度的高阈值。
   1. 在 E 列中，输入适当的公式。有关示例，请参阅[向上箭头或向下箭头指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)或[检查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)。
   1. In the formula cell (Column E), right-click and click **[!UICONTROL Format]** > **[!UICONTROL Indicator]**, then click one of the following:

      * **[!UICONTROL None]**:列出确切的计算，而不是指示符。
      * **[!UICONTROL Check]**:使用复选标记或X指示该值高于或低于您设置的阈值，具体取决于您的公式。 请参阅[检查指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)。
      * **[!UICONTROL Up or Down]**:使用向上或向下箭头指示值是低于低阈值（向下箭头）、高阈值（向上箭头）还是低阈值和高阈值（空白）之间的值。 请参阅[向上箭头或向下箭头指示器](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)。

1. 对要为其创建指示器的其他量度重复步骤 1。

所得到的工作表将如以下示例所示：

![](assets/vis_Worksheet_Alerts.png)

## Up or down indicator {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

对于或 [!DNL Up] ，请使 [!DNL Down indicator]用以下公式：

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

例如：[!DNL =(b2-c2)/(d2-c2)*2-1]

Three outcomes are possible for each metric when using this formula with the [!DNL Up] or [!DNL Down indicator]:

* 如果量度值介于低阈值和高阈值之间，则公式的计算结果为介于 -1 和 1 之间的一个数字（不包括 -1 和 1）。向上箭头或向下箭头不在工作表中显示。
* 如果量度值小于或等于低阈值，则公式的计算结果为小于或等于 -1 的值。量度指示器更改为向下箭头。
* 如果量度值大于或等于高阈值，则公式的计算结果为大于或等于 1 的数字。量度指示器更改为向上箭头。

The following worksheet illustrates what the example formula [!DNL =(b2-c2)/(d2-c2)*2-1] would display:

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Check indicator {#section-98c5298a74f34dcbaaf151549fcc7090}

For the [!DNL Check indicator], you use a formula that indicates whether you want to be notified when the metric value is above or below the threshold you specify. 例如：

* 如果您希望在该值低于您设置的阈值时通知您，则可以使用以下格式：

   * [!DNL threshold - metric]

      例如：[!DNL =(c2-b2)]

* 如果您希望在该值高于您设置的阈值时通知您，则可以使用以下公式：

   * [!DNL metric - threshold]

      例如：[!DNL =(b3-c3)]

当显示复选标记时，该公式的计算结果为正数。当显示 X 时，该公式的计算结果为负数。

There are two possible outcomes for each metric when using the [!DNL Check indicator]:

* 如果公式指示保持量度值高于阈值是比较理想的，则当量度值大于或等于阈值时显示复选标记，当该值小于阈值时显示 X。
* 如果公式指示保持量度值低于阈值是比较理想的，则当量度值小于或等于阈值时显示复选标记，当该值大于阈值时显示 X。

The following worksheet illustrates what the example formulas [!DNL =(c2-b2)] and [!DNL =(b3-c3)] would display:

![](assets/vis_Worksheet_Alerts_Check.png)

