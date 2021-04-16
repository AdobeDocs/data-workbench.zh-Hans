---
description: 活动维度是在“网站营销”用户档案中定义的，用于提供活动分析功能。
title: 营销用户档案维度
uuid: 034b4318-58e6-4638-9b13-fac83ff9f826
exl-id: 93804fba-a44b-4cdc-8d67-d4ec0656e742
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 5%

---

# 营销用户档案维度{#marketing-profile-dimensions}

活动维度是在“网站营销”用户档案中定义的，用于提供活动分析功能。

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
   <td colname="col2"> 重命名为“简单” </td> 
   <td colname="col3">会话 <p>第一行操作 </p></td> 
   <td colname="col4"> 从活动的第一个请求中的值提取的访客标识符。 </td> 
  </tr> 
 </tbody> 
</table>

**自定义营销用户档案Dimension示例**

您可以合并其他数据维度以进一步分析。 通过将附加信息并入为分析而收集的数据流来添加这些维度。 例如，下表包含已添加到不同行业客户部署中的某些自定义营销维度：

| Dimension（自定义） | 描述 |
|---|---|
| 电子邮件活动日期 | 解析电子邮件活动查询字符串中的活动日期（第一个值）。 |
| 电子邮件活动详细信息 | 收集附加到电子邮件活动查询字符串变量的值字符串。 |
| 电子邮件活动区段 | 从电子邮件活动查询字符串解析活动段（第三个值）。 |
| 电子邮件活动类型 | 从电子邮件活动查询字符串解析活动类型（第二个值）。 |
| 营销活动详细信息 | 收集附加到营销活动查询字符串变量的值字符串。 |
| 营销活动所有者 | 从营销活动查询字符串解析活动所有者（第四个值）。 |
| 营销活动源 | 解析营销活动查询字符串中的活动源（第一个值）。 |
| 营销活动类型 | 解析营销活动查询字符串中的活动类型（第二个值）。 |
| PPC活动详细信息 | 收集附加到ppc查询字符串变量的值字符串。 |
