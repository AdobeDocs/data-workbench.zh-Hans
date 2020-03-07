---
description: 置信度图例帮助您确定由于偶然而看到的数字的可能性，并且帮助您了解数据中的可能偏差。
solution: Analytics
title: 置信度图例
topic: Data workbench
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Confidence legends{#confidence-legends}

置信度图例帮助您确定由于偶然而看到的数字的可能性，并且帮助您了解数据中的可能偏差。

即使不对数据进行取样，您也完全确信无法从特定时间段或子集到其他时间段或子集推断数字。置信度图例允许您探究数字落在特定范围内的可能性。

如果您将实际数据视为一个大型实验，那么现实世界仍然包含偶然性，甚至使用确切的数字仍是如此。例如，知道在某个星期二早上 8 点和下午 12 点之间完成某个事务的人数并不意味着在下一个星期二会有相同的人数这样做。

以下置信度图例显示有关“转化”量度的置信度详细信息，而下表提供了有关每个数据点的意义的详细信息。

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>量度或公式 </p> </td> 
   <td colname="col2"> <p>要查看其置信度信息的量度名称或量度表达式。您在工作区中进行的任何选择会反映在图例中。此示例显示有关“转化”量度的详细信息。 </p> <p>有关输入表达式的语法规则的信息，请参阅 <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> 查询语言语法</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>测量值 </p> </td> 
   <td colname="col2"> <p>所收集的实际数据的值。在此示例中，当前选择的转化率为 2.3%。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标准偏差 </p> </td> 
   <td colname="col2"> <p>“测量值”的标准偏差。在此示例中，当前选择的转化率的标准偏差为 0.1%。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>“true”值 </p> </td> 
   <td colname="col2"> <p>“测量值”落在为每个概率列出的范围内的可能性。在此示例中，如果不断重复此“实际实验”，则可以 90% 确定“测量值”将在 2.1% 和 2.4% 之间。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>在分析任何计算的结果时，必须考虑以下注意事项：>
>* 这些数字都是估计值。如果您用不同的数据集重复相同的计算，则会得到不同的结果。这称为随机变差。
>* 根据对所有量度均不正确的常态假定，推断较高的概率。因此，概率 99% 的值不如概率 90% 的值可靠。
>
>
如果需要更确切的数字，则应该咨询统计专家。

## 更改量度或公式 {#section-7f09ff84c3514f26b78d29294e1f03d9}

* In the confidence legend, click in the **[!UICONTROL Metric or Formula]** field and type the desired metric or expression. 有关表达式语法规则，请参 [阅查询语言语法](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。

## 导出到Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

有关导出窗口的信息，请参 [阅导出窗口数据](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)。
