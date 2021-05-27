---
description: 此文件不仅可用作工作表，而且还用作您对实验所作决策的记录。
solution: Analytics,Analytics
title: 实验设计电子表格
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
exl-id: 554790ab-1182-4481-87b0-e768ea769ddf
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# 实验设计电子表格{#experiment-design-spreadsheet}

此文件不仅可用作工作表，而且还用作您对实验所作决策的记录。

如果设计实验时需要帮助，可以使用由Adobe提供的实验设计电子表格（默认命名为VS Controlled Experience Design.xls）。

仅当所讨论的量度被定义为满足某些标准的访客百分比时，实验设计电子表格才能提供有用的统计推断。 也就是说，仅当测试基于访客的量度假设时，它才有用。

**使用实验设计文件设计实验**

1. 如果您有Web或应用程序服务器的管理员访问权限，请导航到Web群集中任何[!DNL Sensor]计算机上的[!DNL Sensor]安装文件夹。 如果您没有管理员访问权限，请联系您的Adobe客户经理以请求文件。
1. 打开VS Controlled Experience Design.xls文件。 （您可以根据需要重命名此文件。）

   以下页面上的电子表格是一个示例，用于说明在准备测试本指南中使用的示例假设时如何填写电子表格。

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. 在此文件中以蓝色输入所有字段的文本或值，下表对此进行了说明。 计算字段在第二个表中定义。

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此字段中…… </th> 
   <th colname="col2" class="entry"> 在“管理工具”中指定分类的 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 实验标题 </td> 
   <td colname="col2"> 实验的描述性名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 实验描述 </td> 
   <td colname="col2"> 实验的文本描述。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 正在研究的量度 </td> 
   <td colname="col2"> <p>实验所基于的量度的名称。 </p> <p>示例：访客转化 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度定义 </td> 
   <td colname="col2"> <p>实验所基于的量度的定义。 </p> <p>格式：访客[X]/访客 </p> <p>示例：<span class="filepath"> Visitors[URI='conversionpage.asp']/Visitors</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 预期开始时间 </td> 
   <td colname="col2"> 您希望开始实验的日期和时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 预期结束时间 </td> 
   <td colname="col2"> 您希望实验结束的日期和时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 适用的选择 </td> 
   <td colname="col2"> （可选）维度名称和元素集，或要进一步划分数据集所依据的范围。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 实验URI </td> 
   <td colname="col2"> 你的假设中涉及的URI。 为控制组定义当前URI以及为测试组创建或将创建的替代URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 应用程序选择的预期量度 </td> 
   <td colname="col2"> 您希望网站使用的量度值的标题。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每日平均访客数 </td> 
   <td colname="col2"> 每天访问您网站的平均访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客转化 </td> 
   <td colname="col2"> 网站的平均访客转化率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 实验将确定测试组的量度名称是否为…… </td> 
   <td colname="col2"> 如何比较量度值的标题。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 是否大于控制组的值？ </td> 
   <td colname="col2"> 如果希望能够得出结论认为测试组的量度在实验期间有所增加，则将此字段设置为True。 将此字段设置为False可减少得出结论所需的访客数。 Adobe建议您将其设置为True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 是否小于控制组的值？ </td> 
   <td colname="col2"> 如果希望能够得出测试组的量度在实验期间下降的结论，请将此字段设置为True。 Adobe建议您将其设置为True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少按（检测级别） </td> 
   <td colname="col2"> 您希望测试组的量度高于或低于控制组的量度的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少具有置信水平 </td> 
   <td colname="col2"> 测试组值的所需置信水平。 置信水平可确定误报数量，以衡量所述预期为真的概率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 和 </td> 
   <td colname="col2"> 测试组值所需的功率级别。 电源级别可确定漏报的数量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客百分比 </td> 
   <td colname="col2"> “访客百分比值”标题。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 测试组 </td> 
   <td colname="col2"> 要包含在测试组中的访客百分比。 您可以播放此数字，直到“访客”部分的“总计（通常为100%）”字段中的值等于或大于“最低需要访客（测试+控制组）”字段中的值，这两者在下表中均有介绍。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 控制组 </td> 
   <td colname="col2"> 您希望包含在控制组中的访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 其他设计说明 </td> 
   <td colname="col2"> 要保存以供将来参考的任何注释。 </td> 
  </tr> 
 </tbody> 
</table>

其余字段均根据您输入的值计算，下表对其进行了说明。

| 字段 | 描述 |
|---|---|
| 应用程序选择的预期量度 | 您希望网站使用的量度值的标题。 |
| 每个时段的预期访客数 | 此字段通常由电子表格自动计算。 它基于以下假设：在大多数情况下，网站接收的新访客比回访访客多。 如果情况不同，则应使用实验期间预期的实际访客数覆盖此单元格的计算。 |
| I类错误的计算Z分数 | 误报结果的Z分数。 这是中间统计计算。 |
| 计算II类错误的Z分数 | 误报结果的Z分数。 这是中间统计计算。 |
| 所需的最低访客数（测试+控制组） | 达到指定置信水平、功率水平和Z分数的实验所需的最小访客数，以“每时段预期访客数”字段中值的百分比表示。 |
| 所需的最低访客数（测试+控制组） | 达到指定的置信水平、功率水平和Z分数所需的最小访客数。 此值必须小于或等于访客部分“总计（通常为100%）”字段中的值。 |
| 最短实验时间（天） | 运行实验以达到指定的置信水平、功率水平和Z分数所需的最小天数。 此计算数字受到的问题与“每时段预期访客数”字段中讨论的问题相同。 对于网站中有许多回访访客的情况，最小实验时间（天）字段是查看大量独特访客所需的预期天数，这些访客数量等于“所需的最小访客数”字段中的值。 |
| 访客 | 访客值的标题。 |
| 测试组 | 测试组中需要的访客数。 |
| 控制组 | 控制组中需要的访客数。 |
| 总计（通常为100%） | 实验所需的访客总数。 此值必须等于或大于“所需的最小访客数（测试+控制组）”字段中的值。 |
| 测试组准确性（在目标置信水平） | 百分比，表示有可能等于指定的置信水平，即为测试组计算的量度的测量值将在其真实值的这一百分比之内。 |
| 控制组的准确性（在目标置信水平） | 百分比，表示有可能等于指定的置信水平，即为控制组计算的量度的测量值将在其真实值的此百分比之内。 |
| Z分数（定位准确度） | 给定值与测试平均值的标准偏差数。 |
| 实际置信水平（在目标间隔） | 达到的实验置信水平。 置信水平衡量所述期望为真的概率。 |
| 实际间隔（在目标置信水平） | 为实验实现的置信区间，它提供可能包括未知群体参数的估计值范围。 此范围是根据一组给定的样本数据计算的。 |

您需要查看所需的最小访客数（测试+控制组）字段中的值。..

![](assets/Experiment_Design_Min_Visitors.png)

并将其与[!DNL Visitors]列的“总计”字段中的值进行比较。

![](assets/Experiment_Design_Total_Visitors.png)

要使您的实验在统计上有效，“总计（通常为100%）”字段中的值必须等于或大于“所需的最小访客数（测试+控制组）”字段中的值。

根据提供的输入，示例工作表显示有10,475位访客需要参与此实验，才能达到输入的95%置信率（这是任何受控实验的最小建议置信率，不过您可以增加此数量）。 目前设计的实验包含30,000位访客，这远高于所需的最低访客数。

如果保持相同的天数，则只要访客总数继续达到或超过所需的最小值，就可以提高置信水平。

1. 保存记录的文件，然后使用文件中的信息，使用实验配置电子表格来配置实验。 有关此电子表格的更多信息，请参阅[配置和部署实验](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。
