---
description: 关于测试运算条件的信息，包括比较、不为空、范围、正则表达式和字符串匹配。
title: 测试运算条件
uuid: 6a117569-1372-4095-972b-76289a45f19e
exl-id: 6c1f521b-a6b9-4bb7-bdfa-56c615b0c916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 67%

---

# 测试运算条件{#test-operation-conditions}

{{eol}}

关于测试运算条件的信息，包括比较、不为空、范围、正则表达式和字符串匹配。

* [比较](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [不为空](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [Range](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [正则表达式](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [字符串匹配](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## 比较 {#section-fb2bdb3838504099b324b9838cdeeaac}

的 [!DNL Compare] 条件会比较字符串值或数值。 对于字符串值的比较，可以指定是否应该考虑大小写。

的参数 [!DNL Compare] 下表描述了条件：

<table id="table_05B1FBB2AED242D99081E62BE2FBEC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Case Sensitive（区分大小写） </td> 
   <td colname="col2">true 或 false。仅当 Type（类型）为 <span class="wintitle">LEXICAL</span>（词法）时才使用。如果设为 false，则大写字母和小写字母被视为是等同的。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关条件的说明。 </td> 
   <td colname="col3"> 评论 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input A（输入 A） </td> 
   <td colname="col2"> 要比较的两个值中的第一个值。此值表示条件中的左操作数。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input B（输入 B） </td> 
   <td colname="col2"> 要比较的两个值中的第二个值。此值表示条件中的右操作数。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operation（运算） </td> 
   <td colname="col2"> <p>比较运算。可用运算（及其含义）如下： 
     <ul id="ul_74F3C298E9CC4FE89897BA0052A9EB9F"> 
      <li id="li_1605FA73474E404A84056D40E7082623"> = 或 ==（输入 A 等于输入 B） </li> 
      <li id="li_F694A262ED7A4787B2A68B877339620C"> &lt;&gt; 或 !=（输入 A 不等于输入 B） </li> 
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt;（输入 A 小于输入 B） </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;=（输入 A 小于或等于输入 B） </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt;（输入 A 大于输入 B） </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;=（输入 A 大于或等于输入 B） </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 类型 </td> 
   <td colname="col2">要进行的比较类型。可用类型为 <span class="wintitle">LEXICAL</span>（词法）、<span class="wintitle">NUMERIC</span>（数值）和 <span class="wintitle">DATETIME</span>（日期时间）。有关类型的描述，请参阅 <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> 测试运算的测试类型</a>. </td> 
   <td colname="col3"> <span class="wintitle"> LEXICAL</span>（词法） </td> 
  </tr> 
 </tbody> 
</table>

此示例使用 [!DNL Compare] 定义条件 [!DNL Log Entry Condition]. 在 Data Workbench Server 读取每条事件数据记录时，将比较数值 x-age 和 55。对于给定的日志条目，如果 x-age 小于等于 55，则该日志条目包含在数据集构建过程中。

![](assets/cfg_Condition_CompareCondition.png)

## 不为空 {#section-1decb9d887894073a1b6b3d985729ac8}

的 [!DNL Not Empty] 条件会检查字段以确定它是包含值还是为空。 对于其值为 [!DNL Input] 字段不为空。

的参数 [!DNL Not Empty] 下表描述了条件：

| 参数 | 描述 | 默认 |
|---|---|---|
| 评论 | 可选。有关条件的说明。 | 评论 |
| Input（输入） | 日志条目中用于检查内容的字段名称。 |  |

此示例采用 x-some-field 作为其输入并测试该字段是否为空。如果该字段填充了内容，则满足条件。

![](assets/cfg_Condition_NotEmpty.png)

## Range {#section-1db31583bb09418b8f49481a897b08a6}

的 [!DNL Range] 条件采用输入字段并确定该字段的值是否在给定的最小(Min)和最大(Max)参数值范围内（包括最小值和最大值）。

的参数 [!DNL Range] 下表描述了条件：

<table id="table_1587D8D333804FC28024C0DFC2F2D4D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Case Sensitive（区分大小写） </td> 
   <td colname="col2">true 或 false。仅当 <span class="wintitle">Type</span>（类型）为 <span class="wintitle">LEXICAL</span>（词法）时才使用。如果设为 false，则大写字母和小写字母被视为是等同的。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关条件的说明。 </td> 
   <td colname="col3"> 评论 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> 日志条目中用作输入的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min（最小） </td> 
   <td colname="col2"> <p>范围的下限。 </p> <p> 此参数的值必须是一个文本值或字符串 - 而不是字段名称。如果对此字段使用日期，则必须指定时区。有关支持的时区缩写列表，请参阅 <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 时区代码</a>. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max（最大） </td> 
   <td colname="col2"> <p>范围的上限。 </p> <p> <p>注意：此参数的值必须是一个文本值或字符串 - 而不是字段名称。如果对此字段使用日期，则必须指定时区。有关支持的时区缩写列表，请参阅 <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 时区代码</a>. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 类型 </td> 
   <td colname="col2">要进行的比较类型。可用类型为 <span class="wintitle">LEXICAL</span>（词法）、<span class="wintitle">NUMERIC</span>（数值）和 <span class="wintitle">DATETIME</span>（日期时间）。有关类型的描述，请参阅 <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> 测试运算的测试类型</a>. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用 [!DNL Range] 定义条件 [!DNL Log Entry Condition]. Data Workbench Server读取每个 [!DNL event data] 记录，它会比较数值x-age和55。 对于给定的日志条目，如果 x-age 至少为 55，则该日志条目包含在数据集构建过程中。此示例与 [!DNL Compare] 条件示例。 请参阅[比较](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)。

>[!NOTE]
>
>如果Min（最小）或Max（最大）参数留空，则Data Workbench Server会使用可用的最小或最大整数值替换。 最小值为零 (0)，最大值为无限大。

![](assets/cfg_Condition_RangeCondition.png)

## 正则表达式 {#section-ae9c016502cb44128760c58f2d2d5297}

的 [!DNL Regular Expression] 条件测试使用正则表达式模式匹配(请参阅 [正则表达式](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c))，以确定指定输入字段的值是否包含与Matches（匹配）参数中指定的模式之一匹配的字符串。

如果输入是字符串矢量，则只使用矢量中的第一个值进行测试。的 [!DNL Regular Expression] 条件会执行完整的字符串比较。 如果要标识子字符串，必须在前面附加“”。&#42;“ ”。

的参数 [!DNL Regular Expression] 下表描述了条件：

<table id="table_0BF5F89F87C9493B8DABA97620074FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Case Sensitive（区分大小写） </td> 
   <td colname="col2"> true 或 false。如果设为 false，则大写字母和小写字母被视为是等同的。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关条件的说明。 </td> 
   <td colname="col3"> 评论 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> 日志条目中用作输入的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 匹配 </td> 
   <td colname="col2"> <p>要匹配输入字段值的正则表达式模式。 </p> <p> <b> 添加正则表达式模式</b> 
     <ol id="ol_6D6467FF74334DEA8E8625C3B155D11D"> 
      <li id="li_9E13A63558FF44749C2E49BD50B7F770">右键单击<span class="uicontrol">匹配</span>。 </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C">单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">正则表达式</span>。 </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">在文本框中输入所需的正则表达式。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例说明了 [!DNL Regular Expression] 匹配从网站流量收集的数据字段的条件。 仅当cs(referrer-query)字段包含与正则表达式匹配的字符串时，该条件才会返回true `campaign=C[1-9][0-9]{4}`. 此正则表达式匹配包含 `campaign=C12345`. 但是，模式与字符串不匹配 `campaign=C0123&` 因为 `C` 不在范围内 `1-9`.

![](assets/cfg_Condition_RegularExpression.png)

## 字符串匹配 {#section-f8d132085c6b4500bfbe4515b848142f}

的 [!DNL String Match] 字符串相等的条件测试。 它采用某个指定字段作为输入，测试每个日志条目中该字段的值是否与该运算的 Matches（匹配）参数中指定的字符串匹配。如果这些区分大小写的匹配字符串中有任何一个与所提供的输入字段中的值相同，则运算将返回 true。如果 [!DNL StringCondition] 不包含任何匹配字符串，则条件将返回 false。如果输入是字符串矢量，则只使用矢量中的第一个值（字符串）进行测试。

<table id="table_BD599BAA5DD54B278813B6C38AC8DE6B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Case Sensitive（区分大小写） </td> 
   <td colname="col2"> true 或 false。如果设为 false，则大写字母和小写字母被视为是等同的。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关条件的说明。 </td> 
   <td colname="col3"> 评论 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> 日志条目中用作输入的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 匹配 </td> 
   <td colname="col2"> <p>要匹配输入字段值的字符串。 </p> <p> <b>添加字符串</b> 
     <ol id="ol_9E32218C771445D88357960475FAD6EB"> 
      <li id="li_A700747858D0470491783E9B3933DAFE">右键单击<span class="uicontrol">匹配</span>。 </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED">单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">字符串</span>。 </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">在文本框中输入所需的字符串。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用从网站流量收集的数据来说明 [!DNL String Match] 条件。 该条件测试输入字段(cs-uri-stem)是否与Matches（匹配）参数中指定的两个字符串中的任一字符串匹配，如果字段cs-uri-stem是精确字符串，则该条件会成功 [!DNL /navigation/footer.asp] 或精确的字符串 [!DNL /navigation/header.asp].

![](assets/cfg_Condition_StringMatch.png)
