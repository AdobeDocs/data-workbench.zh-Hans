---
description: 可以使用“量度编辑器”编辑量度，并将其保存在配置文件的“量度”目录中。
title: 量度表达式的语法
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
exl-id: 27d86fea-6500-4608-aadb-f39058fd3a6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 91%

---

# 量度表达式的语法{#syntax-for-metric-expressions}

可以使用“量度编辑器”编辑量度，并将其保存在配置文件的“量度”目录中。

有关详细信息，请参阅[创建和编辑派生量度](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40)。 量度表达式还可以在工作表中使用。有关详细信息，请参阅 [工作表](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). 可以使用以下语法来定义量度表达式。

注释：

1. 带下划线的字词应该在表达式文本中逐字输入。
1. 表单`{TEXT}?`表示可选文本。
1. 表单`{TEXT}*`表示可能发生零次或多次的文本。
1. 表单`{A | B | C |...}`表示文本，该文本仅包含给定选项之一，如A或B或C....
1. 表单`[A,B)`表示从A到（但不包括B）的数字范围。

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>标识符 </p> </td> 
   <td colname="col2"> <p>标识符会引用一个已命名的量度。有关规范合法标识符的规则，请参阅 <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> 标识符的语法 </a>. </p> <p>示例：Revenue = Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(指标) </p> </td> 
   <td colname="col2"> <p>(Metric) 的结果与 Metric 的结果相同。括号指定表达式中的运算顺序。 </p> <p>示例：Average = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>量度 A 和 B 结果的总和。 </p> <p>示例：Value = Revenue + Cost_Savings </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>量度 A 和 B 结果的差。 </p> <p>示例：利润=收入 — 成本 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>量度 A 和 B 结果的乘积。 </p> <p>示例：Dollars = Cents * 0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>量度 A 和 B 结果的比率。 </p> <p>示例：Revenue_per_Session = Revenue / Sessions </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>对量度 A 求 B 结果次幂的结果。 </p> <p>示例：Area = Width^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric) </p> </td> 
   <td colname="col2"> <p>量度标准偏差的估计值。该值是使用名为 jackknifing 的抽样技术计算的。 </p> <p>此量度对内存有较高要求，不应该在较大的表中使用。 </p> <p>若要使用此语法，您必须具有包含相应属性的 jackknife 维度（名为“jackknife”）。有关详细信息，请联系 Adobe 咨询服务部门。 </p> <p>示例：confidence(Average_Score) </p> <p> <p>注意：置信度量度类型包括 confidence(metric) 和 confidence(metric,jacknife)，在使用 Adobe 的受控实验功能时，这些类型尤为有用。如果在受控试验过程中量度从 12% 跳至 16%，则可以使用置信度标注来计算由于随机变化形成该跳转的差距。这可以帮助您避免由于证据有限而得出错误结论，并且反过来可以保证有问题的更改真实可信。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric, jackknife) </p> </td> 
   <td colname="col2"> <p>量度标准偏差的估计值。该值是使用名为 jackknifing 的抽样技术计算的。此语法让您能够使用具有“jackknife”以外名称的 jackknife 维度确定量度的置信度。 </p> <p>此量度对内存有较高要求，不应该在较大的表中使用。 </p> <p>若要使用此语法，您必须具有包含相应属性的 jackknife 维度（具有“jackknife”以外的名称）。有关详细信息，请联系 Adobe 咨询服务部门。 </p> <p>示例：confidence(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>将您引用的单元格内容视为量度表达式。此语法仅可以在工作表可视化效果中使用。 </p> <p>示例：eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>数学算法函数：量度 X 是参数，量度 B 是基数。 </p> <p>示例：dB = 20*log(Amplitude，10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric[Filter] </p> </td> 
   <td colname="col2"> <p>“Metric where Filter”：给定过滤器所过滤的新量度。 </p> <p>示例：Jan_Sessions = Sessions[ Month=”Jan” ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric by Dimension </p> </td> 
   <td colname="col2"> <p>在“级别”维度上评估的量度。(M by X)[F] 的结果（使用过滤器“F”评估量度“M by X”的结果）是 M[F by X] 的结果（使用过滤器“F by X”评估量度“M”的结果）。 </p> <p>示例：AB_Visitors = </p> <p>(Visitors by Session)[Page="A" and Page="B"] = </p> <p>Visitors[(Page="A" and Page="B") by Session] = </p> <p>同一会话中访问页面 A 和页面 B 的访客数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数字 </p> </td> 
   <td colname="col2"> <p>具有固定值的量度。 </p> <p>示例：Pi = 3.1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Metric) </p> </td> 
   <td colname="col2"> <p>忽略评估量度的任何维度。该量度具有该维度的每个元素的相同值。 </p> <p>示例：Pct_of_Visitors = Visitors / total(Visitors) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Metric) </p> </td> 
   <td colname="col2"> <p>忽略应用于量度的过滤器。该量度未受到选项和其他过滤器的影响。 </p> <p>示例：Benchmark_Sessions = all( Sessions ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric)) </p> </td> 
   <td colname="col2"> <p>忽略所有过滤器和维度。无论应用何种过滤器或维度，在整个给定的配置文件中都具有相同的值。 </p> <p>示例：Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>给出可计数维度（如访客或会话）的计数的量度。 </p> <p>示例：Visitors = sum(One,Visitor) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>给出可计数维度上数值维度总和的量度。将使用数值维度元素的序号值（与格式化的值相对），因此通常需要对结果应用一定的缩放比例。 </p> <p>示例：Value = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>量度 A 和量度 B 的结果中的较小值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>量度 A 和量度 B 的结果中的较大值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>与量度 A 相同的量度，但它使用量度 B 的格式化功能。 </p> </td> 
  </tr> 
 </tbody> 
</table>
