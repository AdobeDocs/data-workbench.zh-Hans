---
description: 正则表达式可以在 Data Workbench 所有搜索字段中使用，包括查询实体面板。
title: 正则表达式
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
exl-id: 75841a70-e78a-429b-b00d-ac107b7a87aa
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 86%

---

# 正则表达式{#regular-expressions}

正则表达式可以在 Data Workbench 所有搜索字段中使用，包括查询实体面板。

* [关于正则表达式](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [正则表达式术语](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [关于文本匹配](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [使用元字符](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [模式提取](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## 关于正则表达式 {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

正则表达式是一种文本模式，它由字母数字字符和称为元字符的特殊字符组合而成，可用于从文本中查找模式并从中提取子字符串。正则表达式广泛用于计算机编程，它是 Perl 之类的语言所必不可少的一部分。

为了识别并提取复杂的字符串模式，Data Workbench Server 会在某些转换和条件中使用正则表达式。以下是有关正则表达式的简要指南。

本附录并未对正则表达式进行全面介绍。这里特别推荐 O&#39;Reilly 出版的《精通正则表达式（第 2 版）》**（由 Jeffrey E. F. Friedl 编写）作为参考。

## 正则表达式术语 {#section-80b0d54f731e448391532ab3eb3c525c}

| 术语 | 定义 |
|---|---|
| 文本 | 文本是正则表达式中用来查找特定字符序列的字符。例如，若要在 [!DNL shop/products.html] 中查找“product”，则字符串“product”便是文本，或我们以文本形式在字符串中查找的内容。 |
| 元字符 | 元字符是一种特殊字符，它在正则表达式的上下文中具有唯一的解释。例如，句点 (.) 就是一个用于匹配任意字符的元字符。 |
| 转义序列 | 转义序列只是一种方式，用于告诉正则表达式引擎我们要使用一个元字符作为文本。转义序列始终以反斜杠字符(`\`)开头。 通过将反斜杠（它也是一个元字符）放置在某个元字符的前面，正则表达式引擎便会将转义的元字符解释为文本。例如，如果要匹配元字符句点(`.`)，则需要使用转义序列。 但是，要匹配字符串168.196.0.11中的某个句点，您可以使用包含反斜杠和句点(`\.`)的正则表达式。 |
| 模式 | 这是正则表达式的简化术语。从本质上讲，正则表达式就是一种尝试匹配目标字符串的模式。 |
| 目标字符串 | 此术语是指我们要在其中搜索以查找所需模式的字符串。 |

## 关于文本匹配 {#section-ec4497e3160c47ba9b828d939761b3e0}

文本匹配采用没有任何转义字符的文本字符串，并在目标字符串中查看它是否为目标字符串的子字符串。

在此示例中，您会了解文本匹配的使用方式。假定数据是从网站流量中收集的，并且 cs(referrer) 字段包含以下值：

`https://www.abc.com/adventurenews/today.html?ad=123AZ45`

若要确定反向链接是否表示某个广告的单击者，您需要查看反向链接是否包含字符串“ad”。您可以只使用文本字符串“ad”来搜索目标字符串，并确定广告是否用于将流量路由到网站。虽然这会匹配目标字符串，但它会在两个位置匹配，从而产生歧义并可能导致误报。

以下 URL 在两个不同的位置都包含字符串“ad”：

`https://www.abc.com/ad vertnews/today.html?ad =123AZ45`

因此，如果您尝试确定哪些会话是由于特定广告营销活动而启动的，则只将文本 ad 作为正则表达式显然是不够的。将文本更改为“ad=”会消除这一歧义，并使表达式只进行一次匹配。但是，即使这样也不足以确保反向链接就是广告营销活动的一部分。请仔细研究以下反向链接：

`https://www.xyz.com/hello.html?pad=something`

您完全无法控制他人可能用来创建网站链接的 URL。文本匹配是一种过于简单的机制，因而无法找到由于广告营销活动而启动的会话。下一节讨论了您该如何使用元字符实现更灵活、更有效的匹配。

## 使用元字符 {#section-e29a804336304ea1ba33d40d60139aa2}

元字符是程序或数据字段中的一种特殊字符，可提供有关其他字符的信息。

| 元字符 | 描述 |
|---|---|
| 。（点号） | 匹配单个字符，例如：`re:x.z` 匹配“xyz”或“xxz”。 |
| *（星号） | 匹配一个或多个字符，例如：`re:Z*`匹配“ZZZ”。 |
| ? （通配符） | 匹配 0 个或 1 个字符以执行最低匹配，例如：`xy?z` 匹配“xy”和“xyz”。 |

其他常见的正则表达式也可以用于创建更加复杂的搜索字符串。

**列表、范围和 OR（或）**

文本匹配允许您查找单个字符串，而括号、短划线和分隔线允许您定义要在目标字符串中查找的内容列表。

<table id="table_18B86955EC3748079E7C176273ADE92B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 对于此元字符... </th>
   <th colname="col2" class="entry"> 正则表达式处理器会... </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 方括号 ([]) </td>
   <td colname="col2"> 将括号内的任意字符与单个字符位置匹配。例如，[AB] 表示匹配字母 A 或字母 B，而 [0123456789] 表示匹配 0 至 9 之间的任意字符。 </td>
  </tr>
  <tr>
   <td colname="col1"> 短划线 (-) </td>
   <td colname="col2"> <p>匹配某个范围的字符。因此，我们可以将 [0123456789] 改写成简单的 [0-9]。 </p> <p> 这可以扩展为多个范围的字符，以及在一组括号内有多个范围。例如，[0-9A-C] 将匹配 0 至 9 和 A 至 C 的字符。 </p> <p> <p>注意：若要将短划线 (-) 在括号内作为文本进行测试，它必须位于最前或最后。例如，[-0-9] 测试 - 和 0 到 9。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 竖线 (|) </td>
   <td colname="col2"> 将两个选项之一匹配给定的目标字符串。例如，b|nat 可匹配 bat 或 nat。 </td>
  </tr>
 </tbody>
</table>

请仔细研究下面的示例：

| 模式 | 字符串 | 匹配 |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| 课程`[A-Z]` | Lesson a | 没有匹配项，因为小写的 a 不在大写的 A 至 Z 范围之内。 |

**求反**

求反用于表示您希望匹配除给定字符以外的任何内容。求反元字符(包括括号或尖角符号(`^`))用作括号内的第一个字符，表示您希望匹配的内容不是括号中的其余字符。 例如，要匹配除分号(`;`)之外的任意字符，您需要编写

[`^;`]

这将匹配除分号以外的任何字符。

**定位**

若要强制匹配目标字符串的开头或结尾，需要使用两个元字符之一。

| 对于此元字符... | 正则表达式处理器会... |
|---|---|
| 音调符号或脱字符号 (`^`) | 匹配字符串的开头。例如，^`[Tt]`他将匹配目标字符串“The Beginn”，但不匹配“This is the begin”。 |
| 美元符号 (`$`) | 匹配字符串的结尾。例如，`[Ee]`nd$将匹配“This is the end”，但不匹配“The end is a special time”。 |

>[!NOTE]
>
>如果正则表达式的开头包含^，结尾包含$，则整个目标字符串必须匹配正则表达式。

**匹配任何内容**

句号 (.) 是一种特殊的元字符，它可以匹配目标字符串中的任意字符。例如，正则表达式`^…$`匹配的任何目标字符串都恰好长三个字符。 正则表达式 &quot;…&quot; 匹配至少包含三个字符的任意目标字符串。

**重复模式**

迭代元字符可让您将一种模式匹配多次。

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 对于此元字符... </th>
   <th colname="col2" class="entry"> 正则表达式处理器会... </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 问号 (?) </td>
   <td colname="col2"> 对紧靠元字符 (?) 之前的字符不匹配任何实例或匹配一个实例。例如，模式 rea?d 匹配 red 和 read。 </td>
  </tr>
  <tr>
   <td colname="col1"> 星号 (*) </td>
   <td colname="col2"> 对紧靠元字符 (*) 之前的字符匹配零个或以上实例。例如，模式 [0–9]* 匹配任意数量的字符 0 至 9（任何整数）。 </td>
  </tr>
  <tr>
   <td colname="col1"> Plus (+) </td>
   <td colname="col2"> 对前面的字符或范围匹配一个或多个实例。例如，模式 thre+ 将匹配 three 而不是 through。 </td>
  </tr>
  <tr>
   <td colname="col1"> {n} </td>
   <td colname="col2"> <p>精确匹配前面的字符或范围 n 次。以下模式与美国电话号码匹配：<code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>。 </p> <p> 虽然这不是最佳模式，但它将确定目标字符串的格式是否正确。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> {n,m} </td>
   <td colname="col2"> 匹配前面的字符最少 n 次，最多 m 次。例如，fo{1,2}d 将匹配 fod 和 food，而不匹配 foood。 </td>
  </tr>
 </tbody>
</table>

## 模式提取 {#section-4389779653b64f6cb7c47615b25c1a79}

模式匹配只是正则表达式的部分功能。正则表达式还提供了一种用于提取目标字符串关键部分的机制。这是通过使用左圆括号和右圆括号完成的。这些提取内容通常用作另一个过程的输入，并通过使用 *%position%* 来访问，其中 position 是一个整数，它表示匹配的括号组的计数。

请仔细研究以下模式提取示例：

<table id="table_BC8D471B966844049FFFCDEC0F183941">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 模式 </th>
   <th colname="col2" class="entry"> 字符串 </th>
   <th colname="col3" class="entry"> 匹配 </th>
   <th colname="col4" class="entry"> 提取 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Win(9[58]) </td>
   <td colname="col2"> OS=Win95 </td>
   <td colname="col3"> Win95 </td>
   <td colname="col4"> %1% = 95 </td>
  </tr>
  <tr>
   <td colname="col1"> (Win)(95|8) </td>
   <td colname="col2"> OS=Win98 </td>
   <td colname="col3"> Win98 </td>
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Mozilla/([0-9])。([0-9]) </td>
   <td colname="col2"> Mozilla/3.0 </td>
   <td colname="col3"> Mozilla/3.03 </td>
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Lesson([A-Z]) </td>
   <td colname="col2"> 教训a </td>
   <td colname="col3"> 没有匹配项，因为小写的 a 不在大写的 A 至 Z 范围之内 </td>
   <td colname="col4"> </td>
  </tr>
 </tbody>
</table>
