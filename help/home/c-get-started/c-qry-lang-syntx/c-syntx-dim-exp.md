---
description: 维度表达式从不单独使用，但是可以在量度或过滤器表达式中调用维度的任何地方使用。
solution: Analytics
title: 维度表达式的语法
topic: Data workbench
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
translation-type: tm+mt
source-git-commit: a276b16565634fea9b693206c8a55b528fada977
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 92%

---


# 维度表达式的语法{#syntax-for-dimension-expressions}

维度表达式从不单独使用，但是可以在量度或过滤器表达式中调用维度的任何地方使用。

1. 带下划线的字词应该在表达式文本中逐字输入。
1. The form `{TEXT}?` represents optional text.
1. The form `{TEXT}*` represents text that may occur zero or more times.
1. The form `{A | B | C |...}` represents text that consists of exactly one of the given options, such as A or B or C....
1. The form `[A,B)` represents a range of numbers, from A up to but not including B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>标识符 </p> </td> 
   <td colname="col2"> <p>标识符会引用一个已命名的维度。有关规范合法标识符的规则，请参阅 <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> 标识符的语法 </a>. </p> <p>示例：Sessions[ Session_Number = “1” ] 是会话数量为“1”的会话数。Session Number 是标识符引用的已命名维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(维度) </p> </td> 
   <td colname="col2"> <p>(Dimension) 的结果与 Dimension 的结果相同。括号指定表达式中的运算顺序。 </p> <p>示例：Sessions[ (Page) = “/home” ] 是访问“/home”页面的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim by Level </p> </td> 
   <td colname="col2"> <p>定义与维度 Dim 具有相同元素的维度，但是通过维度 level 与其他维度相关联。 </p> <p>具体而言，新维度的元素与 level 中和 Dim 的同一元素相同的元素相关联，并与任何其他维度中的元素（这些元素又与 level 中任何元素相关联）相关联。 </p> <p>示例：Sessions[ (Page by Visitor)=”/home” ] 是访问“/home”页面的访客所进行的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift (Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>定义一个与维度 Dim 具有相同元素的维度。如果 Level 的 eth 和 e+Nth 元素与维度组的相同元素相关联，则维度 Level 的 eth 元素与新维度的元素（该元素又与通过 Level 中 e+Nth 元素相关联的 Dim 元素相同）相关联。 </p> <p>示例：Page_Views[ shift(Page, Page_View, Session, 1)=”/home” ] 是在同一会话中浏览的下一页为“/home”的页面查看次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>与 shift(Dim,Level,Group,N) 类似，但如果在维度中出现了空值，则会跳过它们。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> 定义一个根据过滤器列表分类 Level 元素的维度。新维度的元素是以参数形式给出的字符串。Level 的每个元素与过滤器允许 Level 元素的区段维度的第一个元素相关联。这与区段可视化类似。 </p> <p>示例：segment(Visitor, "One-Time Visitors" -&gt; Visitor_Sessions = 1, "Very Loyal Visitors" -&gt; Visitor_Sessions &gt; 10, "Everyone Else" -&gt; True) 创建一个将访客分为三个组的维度：一次性访客指只有一个会话的访客；非常忠诚的访客指具有十个以上会话的访客；其他访客指除前两种访客之外的所有访客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>定义其元素是数字范围（固定大小，如 [0-9], [10-19],...）的维度。Level 的元素与存储段维度（范围包括该级别元素的 Metric 值）的元素相关联。Format 是用于格式化 Metric 元素的 printf 格式字符串。 </p> <p>Example: If Page_Duration_Minutes is a Page View-level dimension representing the number of minutes spent on each page, then bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) is a Session-level dimension representing the number of minutes spent in each Session; its elements are 5 minute intervals <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start 是第一个间隔的起始值（默认：0），Size 是间隔的大小（默认：1）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>定义其元素是给定 ElementName 字符串且与对应 Prefix 字符串集相关联的维度。Level 元素与“前缀”维度的元素相关联，而它又与给定级别元素名称匹配的最长前缀相关联。必须完全匹配以特殊字符“$”结尾的前缀。 </p> <p>例如，prefix(URI, "产品" -&gt; ("/products/"), "服务" -&gt; ("/services/", "/products/service/"), "保修期" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "所有其他项" -&gt; ("/"))) 创建一个将 URI 划分为以下四种类别的维度。在各页上的效果如下所示： </p> <p>/products/warranty.html 转到“保修期”，因为它与 /products/warranty.html$ 前缀完全匹配。 </p> <p>/products/cars/specialcar.html 转到“产品”，因为它与 /products/ 前缀相匹配并且不再是前缀 </p> <p>/products/service/something.html 转到“服务”，因为它与 /products/service/ 前缀相匹配，比 /products/ 前缀长。 </p> <p>/companyinfo/aboutus.html 转到“所有其他项”类别，因为与其相匹配的唯一前缀是“/”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>请参阅 <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> 创建延迟维度 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>定义其元素是所有给定维度元素组合（“笛卡尔积”）的维度。每个元素的名称是由对应输入维度元素的串联组成，并由给定的 Separator 字符串分隔。 </p> <p>例如，如果维度 D1 具有元素 {"a", "b"} 而维度 D2 具有元素 {"x", "y"}，则 cartesian product("-", D1, D2) 具有元素 {"a-x", "a-y", "b-x", "b-y"}。 </p> <p>注意，在内部处理每个输入维度时，假设其元素的数量是二的更高次幂。这将导致具有一些虚拟元素的笛卡尔积。在使用Data WorkbenchAPI时，根据输出格式，这些元素可能会被忽略，或显示为“#nnn”，其中nnn是元素的序号（客户端应忽略它们）。 </p> <p>例如，在上面的示例中，如果 D2 具有三个元素 {"x", "y", "z"}，则在处理它时，将假设它具有四个元素，因而笛卡尔积具有元素 {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}。 </p> <p>如果未给定维度，则结果是具有一个元素“#0”的维度，等同于无维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nearest_countable(Dim) </p> </td> 
   <td colname="col2"> <p>指已经存在的维度：架构中 Dim 的最接近可计数原型。例如，nearest countable(URI) 与 Page_View 相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>定义一个基于非正规维度 Dim 的规范化维度，其元素数最多为 Count 个。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>定义一个具有维度 Dim 元素子集的维度，其元素代表时间段，例如天、星期或年。 </p> <p>子集是一个约为特定时间（常量量度 TimeMetric 的值）的范围，将其解释为自 1970 年 1 月 1 日 UTC 午夜开始的时间值（以秒为单位）。范围具有 Count 个元素，其中最后一个是 Dim 给定元素后的 Offset 元素，其名称是使用给定 FormatString 字符串格式化量度值的结果。FormatString 使用相同的 % 转义作为标准 C 库函数 strftime。 </p> <p>如果 trimToData 为 true，则会删除结果维度开始部分的任何元素，即 Dim 开始前的元素。当它为 false 时，则始终都有 Count 指定的确切元素数。请注意，结果维度的结束部分可能始终会有一些 Dim 中并不实际存在的元素。 </p> <p>WeekStart 为可选参数，如果指定，则必须是 { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" } 中的一项。它将修改 TimeMetric，方法是将其向后移动到与该工作日最接近的日期。 </p> <p>示例：如果 Week 具有元素 { "10/03/10", "10/10/10", ..., "12/12/10" } 并且内置 As Of 量度具有值 1292348109（代表 2010 年 12 月 14 日中午的某个时间），则 last n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") 定义具有元素 { "12/12/10", "12/19/10", "12/23/10", "12/30/10" } 的维度。 </p> <p>示例 2：如果 Week 维度仅有元素 {"12/19/10", "12/26/10", ..., "01/30/11"}，并且 As Of 量度具有与上例相同的值，则 last n(Week, As_Of, "%m/%d/%y", 4, 0, true, "Sun") 给出一个具有元素 {"12/19/10", "12/23/10", "12/30/10"} 的维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>定义具有 Dim 元素子集的维度，其元素代表天。子集是一个约为特定时间（常量量度 TimeMetric 的值）的范围，将其解释为自 1970 年 1 月 1 日 UTC 午夜开始的时间值（以秒为单位）。范围包括的元素对应于指定时间前 nMonths 个月中的每一天。如果 includeThisMonth 为 true，则该范围还包括该月中包含指定时间的每一天。 </p> <p>FormatString 指定 Dim 元素的格式，将“%”转义用作标准 C 库函数 strftime。 </p> <p>如果 trimToData 为 true，则会删除结果维度开始部分的任何元素，即 Dim 开始前的元素。当它为 false 时，则始终都有 Count 指定的确切元素数。请注意，结果维度的结束部分可能始终会有一些 Dim 中并不实际存在的元素。 </p> <p>示例：如果 Day 具有元素 { "01/01/10", "01/02/10", ..., "12/31/10" } 并且内置 As Of 量度具有值 1292348109（代表 2010 年 12 月 14 日中午的某个时间），则 days of previous months(Day, As_Of, "%m/%d/%y", 2, false, false) 将会具有元素 { "10/01/10", "10/02/10", ..., "11/30/10" }。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>与 days of previous months 类似，但元素仅对应与 TimeMetric 指定时间相同月份的日期。如果 allMonth 为 true，则相应月份的每一天对应一个元素；否则，维度将仅包括从相应月份的第一天到包含指定时间的当天的天数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>与 days of previous months 类似，但元素对应于包含 TimeMetric 指定时间的月份之后（而非之前）数月的天数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>定义具有 Dim 元素子集的维度，其元素代表小时。子集是一个约为特定时间（常量量度 TimeMetric 的值）的范围，将其解释为自 1970 年 1 月 1 日 UTC 午夜开始的时间值（以秒为单位）。范围包括的元素对应于 nDaysForward 日期的每个小时，该日期在包含 TimeMetric 指定时间的日期之后。 </p> <p>FormatString 指定 Dim 元素的格式，将“%”转义用作标准 C 库函数 strftime。格式化字符串应始终输出表示传入时间当天开始午夜的字符串。 </p> <p>如果 trimToData 为 true，则会删除结果维度开始部分的任何元素，即 Dim 开始前的元素。当它为 false 时，则始终都有 Count 指定的确切元素数。请注意，结果维度的结束部分可能始终会有一些 Dim 中并不实际存在的元素。 </p> <p>示例：如果 Hour 具有元素 { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" }，并且内置 As Of 量度具有值 1292348109（代表 2010 年 12 月 14 日中午的某个时间），则 hours of day(Hour, As_Of, "%x 00:00", 0, false) 具有元素 { "12/12/10 00:00", "12/12/10 01:00", ..., "12/12/10 23:00" }。 </p> </td> 
  </tr> 
 </tbody> 
</table>

