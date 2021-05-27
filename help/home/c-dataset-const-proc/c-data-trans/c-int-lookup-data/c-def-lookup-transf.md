---
description: 关于可用于将对照数据包含到数据集中的转换的信息。
title: 定义对照转换
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 87%

---

# 定义对照转换{#defining-lookup-transformations}

关于可用于将对照数据包含到数据集中的转换的信息。

请注意，并非所有类型在数据集构建过程的两个阶段都能使用。

* [Categorize](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Categorize {#section-8474376c14e54d14ae73749696ada468}

[!DNL Categorize] 转换使用包含模式字符串/值对的两列对照表。在此转换期间，Data Workbench Server 依次读取每条事件数据记录，并将记录中指定字段的内容与对照表第一列中列出的每个模式字符串进行比较。如果指定的字段与某个模式字符串匹配，Data Workbench Server 会将与该模式字符串关联的值（位于第二列）写入记录中的指定输出字段。

对照表第一列中的字符串可以选择以 ^ 字符开头和/或以 $ 字符结尾，以便强制在开头和/或结尾匹配。此转换不接受使用正则表达式在第一列定义匹配条件。如果输入值是字符串矢量，则每个字符串都将运行转换，结果会附加到输出字符串矢量的后面。

通常，与使用[!DNL Regular Expression]转换实现相同结果相比，[!DNL Categorize]转换更简单、更快。

>[!NOTE]
>
>除非使用[!DNL Case Sensitive]参数另外指定，否则[!DNL Categorize]中使用的子字符串测试区分大小写。

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 转换的描述性名称。可以在此处输入任何名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Case Sensitive（区分大小写） </td> 
   <td colname="col2"> true 或 false。指定子字符串测试是否区分大小写。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 应用此转换的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 默认 </td> 
   <td colname="col2"> 在条件测试通过但分类文件中没有条目匹配输入或给定的日志条目中没有定义输入字段时所使用的默认值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔符 </td> 
   <td colname="col2"> <p>用于在对照文件中分隔列的字符串。必须为一个字符的长度。 </p> <p> 如果按住 Ctrl 键并且右键单击 Delimiter（分隔符）参数内部，则会显示“<span class="wintitle">插入</span>”菜单。此菜单包含通常用作分隔符的特殊字符列表。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple Values（多个值） </td> 
   <td colname="col2"> true 或 false。如果为 true，当文件中的多行匹配输入时，每个匹配项将产生一个值附加到字符串输出矢量的后面。如果为 false，输出中将仅使用文件的第一个匹配行。对于后一种情况，如果输入是一个矢量，输出也将是一个具有同等长度的矢量。如果输入是一个简单的字符串，输出也将是一个简单的字符串。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 文件 </td> 
   <td colname="col2"> 分类文件的路径和名称。相对路径指 Data Workbench Server 的安装目录。此文件通常位于 Data Workbench Server 安装目录的 Lookups 目录中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> 分类文件针对此字段中的值匹配其子字符串，以标识文件中的匹配行。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output（输出） </td> 
   <td colname="col2"> 与结果关联的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**有关Categorize的注意事项**

* 对[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件中定义的[!DNL Categorize]转换中的对照文件所做的更改需要重新转换数据集。 在[!DNL Log Processing.cfg]文件或[!DNL Log Processing Dataset Include]文件中定义的[!DNL Categorize]转换的查找文件不受此限制的约束。 有关重新处理数据的信息，请参阅[重新处理和重新转换](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL Categorize] 文件或文件中定 [!DNL Log Processing.cfg] 义的转换 [!DNL Log Processing Dataset Include] 会在对照文件发生更改时重新加载其对照文件。更改不可向前应用，但它们会应用于更改发生之后读取的所有日志数据。

此示例说明了如何使用 [!DNL Categorize] 转换将对照数据与从网站流量收集的事件数据集成在一起。假定某个特定网站有一些业务部门，并且要求能够基于不同部门生成的流量和值进行查看和比较。您可以创建一个对照文件，其中列出用于标识这些不同部门的子字符串。

对照文件[!DNL Lookups\custommap.txt]包含下表：

| /产品/ | 产品 |
|---|---|
| ^/sports/ | 体育 |
| ^/news/ | 新闻 |
| ... | ... |

此分类文件将所有包含字符串“/products/”的内容映射到值“产品”，将所有以“/sports/”开头的内容映射到值“体育”，并将所有以“/news/”开头的内容映射到值“新闻”。以下分类转换使用 cs-uri-stem 字段中的值作为我们在其中查找匹配子字符串的字符串。转换结果放在 x-custommap 字段中。

![](assets/cfg_TransformationType_Categorize.png)

假定 Multiple Values（多个值）参数设为 false，如果对 cs-uri-stem 给定所列的值，则此示例将为 x-custommap 生成以下值。

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | “体育” |
| [!DNL /sports/products/buy.php] | 产品 |
| [!DNL /news/headlines.php] | 新闻 |
| [!DNL /news/products/subscribe.php] | 产品 |

输出基于子字符串在对照文件中的顺序。例如，cs-uri-stem [!DNL /sports/products/buy.php]返回“Products”。 尽管 URI 主干以“/sports/”开头，但在对照文件中，字符串“/products/”列在“/sports/”的前面。如果 Multiple Values（多个值）参数设为 true，则 x-custommap 将再具有一个值，例如最后一个示例将匹配对照表中的两行：“产品”和“新闻”。

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

[!DNL FlatFileLookup] 转换使用包含任意行数和列数的对照表（但请记住该表将驻留在内存中）。在此类转换期间，Data Workbench Server 依次读取每条事件数据记录，并将记录中指定字段的内容与对照表指定列中的每个值进行比较。如果存在匹配项，Data Workbench Server 会将对照表匹配行中的一个或多个值写入事件数据记录中的一个或多个指定输出字段。

此转换期间使用的对照表从无格式文件填充，该文件的位置在定义转换时指定。

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 转换的描述性名称。可以在此处输入任何名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 应用此转换的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 默认 </td> 
   <td colname="col2"> 在满足条件但对照文件中没有条目匹配输入时所使用的默认值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔符 </td> 
   <td colname="col2"> <p>用于在对照文件中分隔列的字符串。必须为一个字符的长度。 </p> <p> 如果按住 Ctrl 键并且右键单击 Delimiter（分隔符）参数内部，则会显示“<span class="wintitle">插入</span>”菜单。此菜单包含通常用作分隔符的特殊字符列表。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 文件 </td> 
   <td colname="col2"> 对照文件的路径和名称。相对路径指 Data Workbench Server 的安装目录。此文件通常位于 Data Workbench Server 安装目录的 Lookups 目录中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Header Row（标题行） </td> 
   <td colname="col2"> true 或 false。指示表中的第一行是标题行，在处理时要将其忽略。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> <span class="wintitle">Column Name</span>（列名称）是用于将输入与文件中的行匹配的列名称。如果 Header Row（标题行）为 true，它可以是对照文件中某个列的名称。否则，此值必须为要匹配的列从零开始算起的列数。<span class="wintitle">Field Name</span>（字段名称）是用于在对照文件中查找行的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple Values（多个值） </td> 
   <td colname="col2"> <p>true 或 false。确定应返回单个值（一个匹配行）还是多个值（每个匹配行一个）。 </p> <p> <p>注意：如果 <span class="wintitle">Multiple Values</span>（多个值）设为 false，则必须确保没有多个匹配项。当出现多个匹配项时，不能保证返回哪个匹配项。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Outputs（输出） </td> 
   <td colname="col2"> <p>列对象（结果）矢量，其中每个对象由列名称和字段名称定义。 </p> <p> <span class="wintitle">Column Name</span>（列名称）是从中获取输出值的列。如果 <span class="wintitle">Header Row</span>（标题行）为 true，它可以是对照文件中某个列的名称。否则，此值必须为要匹配的列从零开始算起的列数。 </p> <p> <span class="wintitle">Field Name</span>（字段名称）是用于捕获输出的字段名称。请注意，如果 Multiple Values（多个值）参数为 true，它可以是结果矢量，每个结果对应一个标识行。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**注意事项[!DNL FlatFileLookup]**

* 将输入字段与对照文件匹配时始终区分大小写。
* 对[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件中定义的[!DNL FlatFileLookup]转换中的对照文件所做的更改需要重新转换数据集。 在[!DNL Log Processing.cfg]文件或[!DNL Log Processing Dataset Include]文件中定义的[!DNL FlatFileLookup]转换的查找文件不受此限制的约束。 有关重新处理数据的信息，请参阅[重新处理和重新转换](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL FlatFileLookup] 文件或文件中 [!DNL Log Processing.cfg] 的转换 [!DNL Log Processing Dataset Include] 会在对照文件发生更改时重新加载其对照文件。更改不可向前应用，但它们会应用于更改发生之后读取的所有日志数据。

此示例说明了如何使用 [!DNL FlatFileLookup] 转换将对照数据与从网站流量收集的事件数据集成在一起。假定您希望隔离将流量路由到网站的网站合作伙伴，并将合作伙伴 ID 转换为更加易记的名称。然后，可以使用易记名称创建扩展维度和可视化，与用于路由流量的站点对站点关系相比，这些扩展维度和可视化更能清楚地映射业务关系。

该示例转换在cs(referrer-query)字段中搜索PartnerID名称 — 值对，如果找到，则使用查找文件[!DNL Lookups\partners.txt]将PartnerID值与表[!DNL Partner]列中的值进行比较。 如果找到行，则输出字段x-partner-name将被指定标识行[!DNL PrintName]列的名称。

![](assets/cfg_TransformationType_FlatFileLookup.png)

如果对照表包含以下信息：

| ID | 合作伙伴 | 开始时间 | 打印名称 |
|---|---|---|---|
| 1 | P154 | 1999 年 8 月 21 日 | Yahoo |
| 2 | P232 | 2000 年 7 月 10 日 | Microsoft |
| 3 | P945 | 2001 年 1 月 12 日 | Amazon |

以下示例将进行如下转换：

* 如果 cs(referrer)(PartnerID) 返回 P232，将为字段 x-partner-name 指定值“Microsoft”。
* 如果 cs(referrer)(PartnerID) 返回 P100，将为字段 x-partner-name 指定值“No Partner”。
* 如果 cs(referrer)(PartnerID) 未返回任何内容，将为字段 x-partner-name 指定 Default（默认值）参数所指定的值“No Partner”。

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

[!DNL ODBCLookup]转换的操作类似于[!DNL FlatFileLookup]转换。 唯一的区别是此转换期间使用的对照表是从 ODBC 数据库而不是无格式文件填充的。

>[!NOTE]
>
>[!DNL ODBCLookup] 转换只能在数据集构建过程的转换阶段执行。如果可能，Adobe 建议使用 [!DNL FlatFileLookup] 转换代替 [!DNL ODBCLookup] 转换。[!DNL FlatFileLookup] 转换在本质上更可靠，因为它们不依赖于外部系统的可用性。此外，如果对照表位于本地控制的无格式文件中，则修改对照表的风险会较小。

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 转换的描述性名称。可以在此处输入任何名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 应用此转换的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Source Name（数据源名称） </td> 
   <td colname="col2"> 由处理数据集的 Data Workbench Server 计算机管理员提供的 DSN，指的是要从中加载数据的数据库。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database Password（数据库密码） </td> 
   <td colname="col2">连接到数据库时要使用的密码。如果已在<span class="wintitle">数据源管理器</span>中为 DSN 配置了密码，则此参数可以留空。此处提供的任何密码将覆盖在<span class="wintitle">数据源管理器</span>中为 DSN 配置的密码。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database User ID（数据库用户 ID） </td> 
   <td colname="col2">连接到数据库时要使用的用户 ID。如果已在<span class="wintitle">数据源管理器</span>中为 DSN 配置了用户 ID，则此参数可以留空。此处提供的任何用户 ID 将覆盖在<span class="wintitle">数据源管理器</span>中为 DSN 配置的用户 ID。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 默认 </td> 
   <td colname="col2"> 在满足条件但对照文件中没有条目匹配输入时所使用的默认值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Column（输入列） </td> 
   <td colname="col2"> <span class="wintitle">Column Name</span>（列名称）是与输入匹配的数据列名称或 SQL 表达式。<span class="wintitle">Field Name</span>（字段名称）是包含要对照的数据的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple Values（多个值） </td> 
   <td colname="col2"> <p>true 或 false。确定应返回单个值（一个匹配行）还是多个值（每个匹配行一个）。 </p> <p> <p>注意：如果 <span class="wintitle">Multiple Values</span>（多个值）设为 false，则必须确保没有多个匹配项。当出现多个匹配项时，不能保证返回哪个匹配项。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Columns（输出列） </td> 
   <td colname="col2"> <p>列对象（结果）矢量，其中每个对象由列名称和字段名称定义。 </p> <p> <span class="wintitle">Column Name</span>（列名称）是从中获取输出值的列名称或 SQL 表达式。<span class="wintitle">Field Name</span>（字段名称）是用于捕获输出的字段名称。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Table Identifier</span>（表标识符） </td> 
   <td colname="col2"> 一个 SQL 表达式，用于对要从中加载数据的表或视图进行命名。典型的表标识符格式为 SCHEMA.TABLE。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* 数据源名称、[!DNL Database User ID]、[!DNL Database Password]和表标识符参数与ODBC数据源所描述的相同名称的参数相同。 请参阅[ODBC数据源](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)。

* 与ODBC数据源不同，[!DNL ODBCLookup]转换不需要增加ID列。 请参阅[ODBC数据源](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)。 这是因为在数据集处于活动时，不得以任何方式更改对照表的内容。在发生重新转换之前，不会检测对照表或视图中的更改。有关重新处理数据的信息，请参阅 [重新处理和重新转换](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

假定您希望将过时 DNS 记录转换为更新记录。两组记录都存储在 SQL 数据库中。若要执行此任务，需要引用从数据库生成的对照表，并替换过时的 DNS 记录。

我们的示例转换在日志条目中搜索 s-dns 字段，如果找到，将使用对照表 VISUAL.LOOKUP 比较 s-dns 条目与表中 [!DNL OLDDNS] 列的条目。如果在表中找到一行，将为输出字段 s-dns 指定标识行 [!DNL NEWDNS] 列中的更新 DNS 记录条目。

![](assets/cfg_TransformationType_ODBCLookup.png)
