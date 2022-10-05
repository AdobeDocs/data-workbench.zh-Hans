---
description: 营销活动维度在网站营销配置文件中定义，以提供营销活动分析功能。
title: 营销配置文件维度
uuid: 034b4318-58e6-4638-9b13-fac83ff9f826
exl-id: 93804fba-a44b-4cdc-8d67-d4ec0656e742
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 5%

---

# 营销配置文件维度{#marketing-profile-dimensions}

{{eol}}

营销活动维度在网站营销配置文件中定义，以提供营销活动分析功能。

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
   <td colname="col2"> 重命名为简单 </td> 
   <td colname="col3">会话 <p>第一行运算 </p></td> 
   <td colname="col4"> 从访客第一个请求中的值提取的营销活动标识符。 </td> 
  </tr> 
 </tbody> 
</table>

**自定义营销用户档案Dimension示例**

您可以合并其他数据维度以供进一步分析。 通过将附加信息并入为分析而收集的数据流来添加这些维度。 例如，下表包含一些自定义营销维度，这些维度已添加到不同行业客户的部署中：

| Dimension（自定义） | 描述 |
|---|---|
| 电子邮件促销活动日期 | 从电子邮件促销活动查询字符串解析促销活动日期（第一个值）。 |
| 电子邮件营销活动详细信息 | 收集附加到电子邮件促销活动查询字符串变量的值字符串。 |
| 电子邮件促销活动区段 | 从电子邮件促销活动查询字符串解析促销活动区段（第三个值）。 |
| 电子邮件促销活动类型 | 从电子邮件促销活动查询字符串解析促销活动类型（第二个值）。 |
| 营销活动详细信息 | 收集附加到营销活动查询字符串变量的值字符串。 |
| 营销活动所有者 | 从营销活动查询字符串中解析促销活动所有者（第四个值）。 |
| 营销活动来源 | 解析营销活动查询字符串中的促销活动源（第一个值）。 |
| 营销活动类型 | 从营销活动查询字符串中解析促销活动类型（第二个值）。 |
| PPC营销活动详细信息 | 收集附加到ppc查询字符串变量的值字符串。 |
