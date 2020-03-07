---
description: “营销活动”维度在“站点营销”配置文件中定义，以提供营销活动分析功能。
solution: Analytics
title: 营销档案维度
topic: Data workbench
uuid: 034b4318-58e6-4638-9b13-fac83ff9f826
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 营销档案维度{#marketing-profile-dimensions}

“营销活动”维度在“站点营销”配置文件中定义，以提供营销活动分析功能。

<table id="table_27A4B8247F6D4E18BD61041CED7D8805"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 维度 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 级别 </th> 
   <th colname="col4" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 促销活动 </td> 
   <td colname="col2"> 重命名为Simple </td> 
   <td colname="col3">会话 <p>第一行操作 </p></td> 
   <td colname="col4"> 从访客的第一个请求中的值中提取的系列活动标识符。 </td> 
  </tr> 
 </tbody> 
</table>

**自定义营销配置文件维的示例**

您可以合并其他数据维度以进一步分析。 通过将附加信息并入收集用于分析的数据流中来添加这些维度。 例如，下表包含已为不同行业的客户添加的一些自定义营销维度：

| Dimension（自定义） | 描述 |
|---|---|
| 电子邮件营销活动日期 | 从电子邮件营销活动查询字符串分析营销活动日期（第一个值）。 |
| 电子邮件营销活动详细信息 | 收集附加到电子邮件营销活动查询字符串变量的值字符串。 |
| 电子邮件营销活动区段 | 从电子邮件营销活动查询字符串分析营销活动区段（第三个值）。 |
| 电子邮件营销活动类型 | 从电子邮件营销活动查询字符串分析营销活动类型（第二个值）。 |
| 营销活动详细信息 | 收集附加到营销活动查询字符串变量的值字符串。 |
| 营销活动所有者 | 从营销活动查询字符串分析营销活动所有者（第四个值）。 |
| 营销活动源 | 分析营销活动查询字符串中的营销活动源（第一个值）。 |
| 营销活动类型 | 从营销活动查询字符串分析系列活动类型（第二个值）。 |
| PPC营销活动详细信息 | 收集附加到ppc查询字符串变量的值字符串。 |

