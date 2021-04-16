---
description: Data Workbench Server (InsightServer64.exe) 可以从任何具有 ODBC 3.0 兼容驱动程序的 SQL 数据库（例如 Oracle 或 Microsoft SQL Server）中读取事件数据。
title: ODBC 数据源
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 89%

---

# ODBC 数据源{#odbc-data-sources}

Data Workbench Server (InsightServer64.exe) 可以从任何具有 ODBC 3.0 兼容驱动程序的 SQL 数据库（例如 Oracle 或 Microsoft SQL Server）中读取事件数据。

Data Workbench Server 的 ODBC 支持与当前支持从传感器或从外部流程生成的日志文件加载数据类似。不过，该支持存在一些其他注意事项和限制：

* Data Workbench Server 的 ODBC 支持与群集功能兼容。数据会在所有处理服务器之间分发，并且所有后续处理（包括查询处理）可以充分利用群集功能。
* ODBC 支持依赖于第三方 ODBC 驱动程序。要使 ODBC 支持有效，必须使用 Adobe 平台以外的工具在运行 Data Workbench Server 的计算机上对这些驱动程序进行配置。Data Workbench 计算机不需要任何其他配置。
* 从中加载数据的表或视图必须具有递增 ID 列。对于任何行，当有新行插入数据库时，此列（可能是表中的实际列或任何 SQL 列表达式）中的值不得减小。如果违反此限制，数据将会丢失。为了充分发挥性能，此列或列表达式中需要使用索引。

   >[!NOTE]
   >
   >多行在[!DNL Increasing ID]列中可能具有相同的值。 出现这种情况的一种可能性是时间戳列的精确度不高。

* Data Workbench Server 无法加载数据较长的列（数据超出了由正在使用的特定数据库应用程序确定的某个长度）。
* 从数据库检索数据的速度要慢于从磁盘文件中读取数据。与数据来自“传感器”或其他磁盘文件且大小相等的数据集相比，从 ODBC 源加载数据的数据集花费的处理时间会更长些（尤其是在重新处理时）。

有关重新处理数据的信息，请参阅 [重新处理和重新转换](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**为ODBC配置Insight Server[!DNL event data]**

如果将 Data Workbench Server 配置为从 SQL 数据库加载数据，则您需要首先依次执行下列步骤：

1. 在处理数据集的 Data Workbench Server 计算机上安装相应的数据库客户端软件（包括 ODBC 驱动程序）。

   >[!NOTE]
   >
   >如果加载ODBC事件数据以在Data Workbench Server群集上进行处理，则必须在群集中的所有处理服务器上安装数据库客户端软件。 有关在群集中指定处理服务器的信息，请参阅《服务器产品安装和管理指南》**。

1. 使用用于 Windows 的 ODBC 数据源管理器配置数据源。

   请务必注意，Data Workbench Server (InsightServer64.exe) 必须作为一项 Windows 服务运行。因此，数据源通常必须配置为系统 DSN（而不是用户 DSN），以便 Data Workbench Server 能够使用它。您可以在数据库软件的相关文档中找到有关此配置步骤的详细信息。

在相应的Data Workbench Server计算机上安装数据库客户端软件后，可以通过编辑[!DNL Log Processing]配置文件中所需用户档案的相应参数，将数据集配置为使用ODBC数据源。

## 参数 {#section-15c0218d93364693a565f2609a12f73e}

对于使用开放式数据库连接 (ODBC) 标准的数据库中的数据，有以下参数可用：

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> ODBC 源的标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Source Name（数据源名称） </td> 
   <td colname="col2"> 由处理数据集的 Data Workbench Server 计算机管理员提供的 DSN，指的是要从中加载数据的数据库。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database Password（数据库密码） </td> 
   <td colname="col2"> 连接到数据库时要使用的密码。如果已在<span class="wintitle">数据源管理器</span>中为 DSN 配置了密码，则此参数可以留空。此处提供的任何密码将覆盖在<span class="wintitle">数据源管理器</span>中为 DSN 配置的密码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database User ID（数据库用户 ID） </td> 
   <td colname="col2"> 连接到数据库时要使用的用户 ID。如果已在<span class="wintitle">数据源管理器</span>中为 DSN 配置了用户 ID，则此参数可以留空。此处提供的任何用户 ID 将覆盖在<span class="wintitle">数据源管理器</span>中为 DSN 配置的用户 ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fields（字段） </td> 
   <td colname="col2"> 列对象的矢量，用于指定从数据库中的数据列到 Data Workbench Server 执行引擎中数据字段的映射。每列都具有“<span class="wintitle">列名称</span>”和“<span class="wintitle">字段名称</span>”条目。“<span class="wintitle">列名称</span>”是一个 SQL 列表达式，必须在由“<span class="wintitle">表标识符</span>”所标识的表上下文中有效（如上所述）。它可以是列名称，也可以是基于表中任意列数的任何 SQL 表达式。如果要以一种不会损失精确度的方式来将某些数据类型的值转换为字符串，则可能需要使用格式设置功能。系统会使用数据库的默认格式设置方法来将所有数据隐式转换为字符串；如果未使用隐式格式设置表达式，这样可能会导致某些列数据类型（例如日期/时间数据类型）丢失数据。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Increasing ID Column（递增 ID 列） </td> 
   <td colname="col2"> <p>列名称或 SQL 列表达式，符合在添加新行时会增大（或者至少不会减小）的条件。也就是说，如果 B 行添加到表中的时间晚于 A 行，则 B 行中此列（或列表达式）的值必须大于（根据数据库的本机排列顺序）A 行中对应的值。 </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> “<span class="wintitle">递增 ID 列</span>”名称可以与现有列的名称相同，但并不要求这样。 </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> 假定此表达式的数据类型为 SQL 字符。如果实际递增 ID 列为其他某种数据类型，则此值必须是列表达式才能将其转换为字符串。由于这通常意味着将进行字典式（逐个字符）比较，因此请务必谨慎设置值的格式。 </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> 表达式将用在 SQL ORDER BY 子句中，并在 SQL WHERE 子句中进行比较。请务必在将要使用的确切列表达式中构建索引，这一点极为重要。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Source ID（日志源 ID） </td> 
   <td colname="col2"> <p>此参数的值可以是任意字符串。如果指定了某个值，则此参数可让您将来自不同日志源的日志条目区分开，以便进行源识别或目标处理。x-log-source-id 字段填充了用于识别每个日志条目的日志源的值。例如，如果您想要识别名为 ODBCSource01 的 ODBC 源中的日志条目，则可以键入 <span class="filepath">from ODBCSource01</span>，然后该字符串将会传递到该源中每个日志条目的 x-log-source-id 字段。 </p> <p> 有关x-log-source-id字段的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f">事件数据记录字段</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Run On Server（运行服务器） </td> 
   <td colname="col2"> 处理服务器在 <span class="filepath">profile.cfg</span> 文件中的索引值，该服务器将生成 ODBC 查询以从数据库中获取数据。（<span class="filepath">profile.cfg</span> 文件中的 Processing Servers（处理服务器）参数列出了数据集的所有处理服务器，并且每个服务器都具有一个索引值，第一个值为 0。）默认值为 0。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Table Identifier（表标识符） </td> 
   <td colname="col2"> 一个 SQL 表达式，用于对要从中加载数据的表或视图进行命名。典型的表标识符格式为 SCHEMA.TABLE。 </td> 
  </tr> 
 </tbody> 
</table>

此示例显示了Data Workbench中具有ODBC数据源的[!DNL Log Processing]配置窗口。 此数据源从[!DNL Data Source Name]为&quot;VSTestO&quot;的数据库中名为[!DNL VISUAL.VSL]的表中获取数据。 五 (5) 个列对象（[!DNL Fields]（字段））将数据库中数据列的数据映射到 Data Workbench Server。

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
