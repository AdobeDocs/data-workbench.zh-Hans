---
description: “比较”条件和“范围”条件需要您指定对条件所进行的比较类型。
title: 测试运算的测试类型
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 98%

---

# 测试运算的测试类型{#test-types-for-test-operations}

“比较”条件和“范围”条件需要您指定对条件所进行的比较类型。

下表介绍了可用类型（[!DNL LEXICAL]、[!DNL NUMERIC]和[!DNL DATETIME]）。

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 测试类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 注释 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTEGER</span>（整数） </p> </td> 
   <td colname="col2"> <p>首先将输入字段变为一个整数。如果无法执行此操作，则使用零值。如果获得的整数输入值大于或等于指定的最小值，且小于或等于指定的最大值，则测试返回 true。 </p> </td> 
   <td colname="col3"> <p>如果最小字段或最大字段保留为空，则系统会使用可用于 64 位带符号整数的相应最小或最大值。 </p> <p> 如果条件中指定的最小或最大值未成功解析为整数值，则系统会将其替换为零，而不会停止处理数据集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span>（日期时间） </p> </td> 
   <td colname="col2"> <p>首先将输入字段变为一个日期。如果输入字段无法变为一个有效日期，则条件测试返回 false。如果字段可以变为一个日期，则仅当输入日期不早于指定的最小日期且不晚于指定的最大日期时，测试才返回 true。 </p> </td> 
   <td colname="col3"> <p>如果最小日期和最大日期均无效，将不会构建数据集。 </p> <p> 如果未提供最小日期或最大日期，则系统会将其替换为相应的最小日期（1600 年 1 月 1 日）或最大日期（24 世纪的某个日期）。 </p> <p> Adobe 建议对 <span class="wintitle">DATETIME</span>（日期时间）使用下列格式之一： </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> January 1 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> Jan 1 2013 HH:MM:SS GMT </li> 
    </ul> <p> 时区在未指定的情况下会默认为 GMT。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXICAL</span>（词法） </p> </td> 
   <td colname="col2"> <p>仅当输入字段在词法上大于或等于最小值中指定的字符串，且小于或等于最大值中指定的字符串时，才返回 true。 </p> </td> 
   <td colname="col3"> <p>词法比较使用字符串中字符的 ASCII 值从左向右移动来比较字符。对于首字符不匹配的字符串，具有较大 ASCII 值的字符串会被视为两个字符串中的较大者。如果一个字符串短于另一个字符串，但在该点处之前的所有字符都是相同的，则较长的字符串会被视为两个字符串中的较大者。如果两个字符串逐个字符均对等，并且长度完全相同，则它们被视为在词法上相等。 </p> </td> 
  </tr> 
 </tbody> 
</table>
