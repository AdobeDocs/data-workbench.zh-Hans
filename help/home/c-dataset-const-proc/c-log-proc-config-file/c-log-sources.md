---
description: 日志源是指包含要用于构建数据集的数据的文件。
title: 日志源
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 83%

---

# 日志源{#log-sources}

日志源是指包含要用于构建数据集的数据的文件。

日志源中提供的数据称为事件数据，因为每条数据记录都表示一条交易记录或一个事件的单个实例。Data Workbench Server可以处理从由[!DNL Sensors]收集的数据派生或从其他数据源提取的日志源。

* **由[!DNL Sensors]收集的数据：**由[!DNL Sensors]从HTTP和应用程序服务器收集的数据将传输到Data Workbench Server，Data Workbench Server会将数据转换为高度压缩的日志([!DNL .vsl])文件。 请参阅[传感器文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)。

* **Insight Server 提取的数据：** Data Workbench Server 会读取无格式文件、XML 文件或 ODBC 兼容数据库中包含的事件数据，并使用其解码器提取所需的数据元素。此类事件数据不必驻留在内存中，但包含数据的记录必须包含跟踪ID。 请参阅[日志文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)、[XML日志源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)和[ODBC数据源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)。

**添加日志源**

1. 在Data Workbench中打开[!DNL Log Processing.cfg]。
1. 右键单击&#x200B;**[!UICONTROL Log Sources]**，然后单击&#x200B;**[!UICONTROL Add New]**。

1. 选择下列选项之一：

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. 用于定义数据集的具体参数会因数据集的配置过程中要使用的日志源类型而有所不同。请按照相应的日志源所对应的章节中的说明指定参数：

   * [传感器文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [日志文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [XML 日志源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [ODBC 数据源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. 当您在 [!DNL Log Processing.cfg] 文件中定义日志源（并对其他参数做出更改）之后，将该文件保存在本地，然后将其保存到 Data Workbench Server 上的数据集配置文件中。

   >[!NOTE]
   >
   >Data Workbench Server [!DNL File Server Unit]可接收和存储[!DNL Sensor]文件、日志文件和XML文件，并将它们提供给Data Workbench Server的[!DNL Data Processing Units]来构建数据集。 请参阅[配置Insight Server文件服务器单元](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d)。

   可以从[!DNL Transformation Dependency Map]打开任何日志源的配置。 有关[!DNL Transformation Dependency Map]的信息，请参阅[数据集配置工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

<!--
c_sensor_files.xml
-->

## 要求 {#section-d5901a4872774ad5bd01a18db114f1f2}

由[!DNL Sensors]从HTTP和应用程序服务器收集的事件数据将传输到Data Workbench Server，Data Workbench Server会将数据转换为高度压缩的日志([!DNL .vsl])文件。 [!DNL .vsl]文件格式由Data Workbench Server管理，每个文件都有以下格式名称：

YYYYMMDD-*SENSORID*.VSL

其中YYYYMMDD是文件的日期，而&#x200B;*SENSORID*&#x200B;是（由您的组织分配）的名称，指示哪个[!DNL Sensor]收集数据并将数据传输到Data Workbench Server。

## 参数 {#section-5c3f1e341c284486aeba3452057da7f3}

对于[!DNL Sensor]文件，可使用以下参数：

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Log Paths（日志路径） </td> 
   <td colname="col2"> <p>存储 <span class="filepath">.vsl</span> 文件的目录。默认位置为 Logs 目录。相对路径指 Data Workbench Server 的安装目录。 </p> <p>您可以使用通配符指定要处理的 <span class="filepath">.vsl</span> 文件： 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * 匹配任意数量的字符 </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? 匹配单个字符 </li> 
     </ul> </p> <p> 例如，日志路径 <span class="filepath">Logs\*.vsl</span> 匹配的是 Logs 目录中以 <span class="filepath">.vsl</span> 结尾的所有文件。日志路径 <span class="filepath">Logs\*-SENSOR?.vsl</span> 匹配的是 Logs 目录中带有任何日期 (YYYYMMDD) 且在 SENSOR 后面跟有一个字符（例如 SENSOR1）的文件。 </p> <p> 如果您想要搜索指定路径的所有子目录，则必须将 Recursive（递归）参数设为 true。 </p> <p> <p>注意：如果要从 Data Workbench Server 的<span class="wintitle">文件服务器单元</span>中读取文件，则必须在 Log Paths（日志路径）参数中输入相应的 URI。例如，<span class="filepath">URI/Logs/*-*.vsl</span> 匹配的是 Logs 目录中的所有 <span class="filepath">.vsl</span> 文件。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d">配置Insight Server文件服务器单元</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Server（日志服务器） </td> 
   <td colname="col2">连接到文件服务器所需的信息（地址、名称、端口等）。如果 Log Server（日志服务器）参数中有一个条目，则 <span class="wintitle">Log Paths</span>（日志路径）会被解释为 URI。否则，它们会被解释为本地路径。请参阅 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 配置 Insight Server 文件服务器单元</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Source ID（日志源 ID） </td> 
   <td colname="col2"> <p>此参数的值可以是任意字符串。如果指定了某个值，则此参数可让您将来自不同日志源的日志条目区分开，以便进行源识别或目标处理。x-log-source-id 字段填充了用于识别每个日志条目的日志源的值。例如，如果您想要识别名为 VSensor01 的<span class="wintitle">传感器</span>中的日志条目，则可以键入 <span class="filepath">from VSensor01</span>，然后该字符串将会传递到该源中每个日志条目的 x-log-source-id 字段。 </p> <p> 有关x-log-source-id字段的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f">事件数据记录字段</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursive（递归） </td> 
   <td colname="col2"> true 或 false。如果设为 true，则系统会在“<span class="wintitle">日志路径</span>”中指定的每个路径的所有子目录中搜索与指定文件名或通配符模式匹配的文件。默认值为 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use Start/End Times（使用开始/结束时间） </td> 
   <td colname="col2"> <p>true 或 false。如果设为 true，并且指定了“开始时间”或“结束时间”，则此日志源的所有文件名称必须以 ISO 格式 (YYYYMMDD) 的日期开头。假定每个文件都包含某一 GMT 日期（例如，时间范围从某一天的 0000 GMT 开始，到第二天的 0000 GMT 结束）的数据。如果日志源的文件包含的数据与 GMT 日期不对应，则此参数必须设为 false 才能避免产生错误结果。 </p> <p> <p>注意：默认情况下，包含<span class="filepath">传感器</span>收集数据的 <span class="wintitle">.vsl</span> 文件会自动符合上述命名和时间范围要求。如果将此参数设为 true，则 Data Workbench Server 会始终处理名称中包含的 ISO 日期介于指定“开始时间”和“结束时间”之间的文件数据。如果您将此参数设为 false，则 Data Workbench Server 会在日志处理过程中读取所有 <span class="filepath">.vsl</span> 文件，以确定哪些文件包含介于“开始时间”和“结束时间”之间的数据。 </p> </p> <p> 有关“开始时间”和“结束时间”参数的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">过滤器</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>请勿使用[!DNL Sensor]数据源的配置参数来确定数据集中应包括日志文件中的哪些日志条目。 而是将数据源设置为指向目录内的所有日志文件。然后使用 [!DNL Log Processing.cfg] 的 Start Time（开始时间）和 End Time（结束时间）参数确定构建数据集时使用的日志条目。请参阅[数据过滤器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d)。

<!--
c_log_files.xml
-->

包含事件数据的文件必须满足以下条件：

* 文件中的每条事件数据记录必须由一行表示。
* 记录中的字段无论是否为空，都必须以 ASCII 分隔符分隔。Data Workbench Server 不要求使用特定的分隔符。您可以使用任意不属于行结束字符，并且不会出现在事件数据本身任何位置的字符。
* 文件中的每条记录必须包含：

   * 跟踪 ID
   * 时间戳

* 若要指定数据处理的开始时间和结束时间，每个文件名必须采用以下格式：

   * [!DNL YYYYMMDD-SOURCE.log]

   其中 *YYYYMMDD* 是文件中所有数据的格林威治标准时间 (GMT) 日期；*SOURCE* 是一个变量，用于识别文件中包含数据的源。

   >[!NOTE]
   >
   >请联系Adobe咨询服务部门，以查看您计划合并到数据集中的日志文件。

## 参数 {#section-83a861ac24954d54bbb9530e4d8bf23c}

对于日志文件日志源，有下表中的参数可用。

>[!NOTE]
>
>处理日志文件日志源需要在[!DNL Log Processing Dataset Include]文件中定义的附加参数，该文件包含包含在[!DNL Log Processing.cfg]文件中的参数子集以及用于定义解码器以从日志文件中提取数据的特殊参数。 有关为日志文件日志源定义解码器的信息，请参阅[文本文件解码器组](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd)。

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 日志文件源的标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Paths（日志路径） </td> 
   <td colname="col2"> <p>存储日志文件的目录。默认位置为 Logs 目录。相对路径指 Data Workbench Server 的安装目录。 </p> <p> 您可以使用通配符指定要处理的日志文件： 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * 匹配任意数量的字符。 </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? 匹配单个字符。 </li> 
     </ul> </p> <p> 例如，日志路径 <span class="filepath">Logs\*.log</span> 匹配 Logs 目录中以 <span class="filepath">.log</span> 结尾的所有文件。 </p> <p> 如果您想要搜索指定路径的所有子目录，则必须将 Recursive（递归）参数设为 true。 </p> <p> 如果要从 Data Workbench Server 的<span class="wintitle">文件服务器单元</span>中读取文件，则必须在 Log Paths（日志路径）参数中输入相应的 URI。例如，<span class="filepath">URI/Logs/*.log</span> 匹配的是 Logs 目录中的所有 <span class="filepath">.log</span> 文件。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d">配置Insight Server文件服务器单元</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Server（日志服务器） </td> 
   <td colname="col2"> 连接到文件服务器所需的信息（地址、名称、端口等）。如果 Log Server（日志服务器）参数中有一个条目，则 <span class="wintitle">Log Paths</span>（日志路径）会被解释为 URI。否则，它们会被解释为本地路径。请参阅 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 配置 Insight Server 文件服务器单元</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressed（已压缩） </td> 
   <td colname="col2"> true 或 false。如果 Data Workbench Server 要读取的日志文件已压缩为 gzip 文件，则此值应该设为 true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoder Group（解码器组） </td> 
   <td colname="col2"> 要应用于日志文件日志源的文本文件解码器组的名称。此名称必须与<span class="wintitle">日志处理数据集包含</span>文件中指定的相应文本文件解码器组的名称完全匹配。请参阅<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd">文本文件解码器组</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Source ID（日志源 ID） </td> 
   <td colname="col2"> <p>此参数的值可以是任意字符串。如果指定了某个值，则此参数可让您将来自不同日志源的日志条目区分开，以便进行源识别或目标处理。x-log-source-id 字段填充了用于识别每个日志条目的日志源的值。例如，如果您想要识别名为 LogFile01 的日志文件源中的日志条目，则可以键入 <span class="filepath">from LogFile01</span>，然后该字符串将会传递到该源中每个日志条目的 x-log-source-id 字段。 </p> <p> 有关x-log-source-id字段的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f">事件数据记录字段</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mask Pattern（掩码模式） </td> 
   <td colname="col2"> <p>具有单个捕获子模式的正则表达式，可提取用于识别一系列日志文件源的一致名称。仅考虑文件名。对于正则表达式匹配，不考虑路径和扩展名。如果您没有指定<span class="wintitle">掩码模式</span>，则系统会自动生成掩码。 </p> <p> 对于 <span class="filepath">Logs\010105server1.log</span> 和 <span class="filepath">Logs\010105server2.log</span> 文件，<span class="wintitle">掩码模式</span>将为 <code>[0-9]{6}(.*)</code>. 此模式从以上文件名中提取字符串“server1”或“server2”。 </p> <p> 请参阅 <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> 正则表达式</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursive（递归） </td> 
   <td colname="col2"> true 或 false。如果此参数设为 true，则系统会在“<span class="wintitle">日志路径</span>”中指定的每个路径的所有子目录中搜索与指定文件名或通配符模式匹配的文件。默认值为 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reject File（拒绝文件） </td> 
   <td colname="col2"> 包含的日志条目不符合解码器条件的文件路径和名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use Start/End Times（使用开始/结束时间） </td> 
   <td colname="col2"> <p>true 或 false。如果此参数设为 true，并且指定了“开始时间”或“结束时间”，则此日志源的所有文件名称必须以 ISO 格式 (YYYYMMDD) 的日期开头。假定每个文件都包含某一 GMT 日期（例如，时间范围从某一天的 0000 GMT 开始，到第二天的 0000 GMT 结束）的数据。如果日志源的文件名没有以 ISO 日期开头，或者文件包含的数据与 GMT 日期不对应，则此参数必须设为 false 才能避免产生错误结果。 </p> <p> <p>注意：如果日志文件满足上述命名和时间范围要求，并且您将此参数设为 true，则指定的文本文件解码器组会将读取的文件限制为名称中含有的 ISO 日期介于指定“开始时间”和“结束时间”之间的文件。如果您将此参数设为 false，则 Data Workbench Server 会在日志处理过程中读取所有日志文件，以确定哪些文件包含介于“开始时间”和“结束时间”之间的数据。 </p> </p> <p> 有关 Start Time（开始时间）和 End Time（结束时间）参数的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">数据过滤器</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在此示例中，数据集从两种类型的日志源构建。

日志源0指定从[!DNL Sensor]捕获的事件数据生成的日志文件。 此数据源指向名为“Logs”的目录，并指向该目录中具有[!DNL .vsl]文件扩展名的所有文件。

日志源1指向“日志”目录中文件扩展名为[!DNL .txt]的所有文件。 此日志源的解码器组称为“文本日志”。

![](assets/cfg_LogProcessing_LogSources.png)

在定义了数据集的数据源之后，请勿删除或移动日志文件。只能将新创建的日志文件添加到数据源的目录中。

<!--
c_xml_log_sources.xml
-->

包含事件数据的文件必须满足以下条件：

* 事件数据必须包含在格式正确且具有相应父子关系的 XML 文件中。
* 每种 XML 文件格式都必须具有唯一的解码器组。有关构建解码器组的信息，请参阅 [XML 解码器组](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* 文件中的每条访客记录必须包含：

   * 跟踪 ID
   * 时间戳

* 若要指定数据处理的开始时间和结束时间，每个文件名必须采用以下格式：

[!DNL YYYYMMDD-SOURCE.log]

其中 *YYYYMMDD* 是文件中所有数据的格林威治标准时间 (GMT) 日期；*SOURCE* 是一个变量，用于识别文件中包含数据的源。

有关符合这些要求的 XML 文件的示例，请参阅 [XML 解码器组](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>请联系Adobe咨询服务部门以查看您计划合并到数据集中的XML日志文件。

## 参数 {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

对于 XML 日志源，有下表中的参数可用。

>[!NOTE]
>
>处理XML日志源需要在[!DNL Log Processing Dataset Include]文件中定义的附加参数，该文件包含包含在[!DNL Log Processing.cfg]文件中的参数子集以及用于定义解码器以从XML文件提取数据的特殊参数。 有关为XML日志源定义解码器的信息，请参阅[XML解码器组](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3)。

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> XML 日志源的标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Paths（日志路径） </td> 
   <td colname="col2"> <p>存储 XML 日志源的目录。默认位置为 Logs 目录。相对路径指 Data Workbench Server 的安装目录。 </p> <p> 您可以使用通配符指定要处理的 XML 日志源： 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * 匹配任意数量的字符 </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? 匹配单个字符 </li> 
     </ul> </p> <p>例如，日志路径 <span class="filepath">Logs\*.xml</span> 匹配的是 Logs 目录中以 <span class="filepath">.xml</span> 结尾的所有文件。 </p> <p> 如果您想要搜索指定路径的所有子目录，则必须将“<span class="wintitle">递归</span>”字段设为 true。 </p> <p> <p>注意：如果要从 Data Workbench Server 的<span class="wintitle">文件服务器单元</span>中读取文件，则必须在 <span class="wintitle">Log Paths</span>（日志路径）字段中输入相应的 URI。例如，<span class="filepath">URI/Logs/*.xml</span> 匹配的是 Logs 目录中的所有 <span class="filepath">.xml</span> 文件。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d">配置Insight Server文件服务器单元</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Server（日志服务器） </td> 
   <td colname="col2"> 连接到文件服务器所需的信息（地址、名称、端口等）。如果 <span class="wintitle">Log Server</span>（日志服务器）字段中有一个条目，则 <span class="wintitle">Log Paths</span>（日志路径）会被解释为 URI。否则，它们会被解释为本地路径。请参阅 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 配置 Insight Server 文件服务器单元</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressed（已压缩） </td> 
   <td colname="col2"> true 或 false。如果 Data Workbench Server 要读取的 XML 日志源已压缩为 gzip 文件，则此值应该设为 true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoder Group（解码器组） </td> 
   <td colname="col2"> 要应用于 XML 日志源的 XML 解码器组的名称。此名称必须与<span class="wintitle">日志处理数据集包含</span>文件中指定的相应 XML 解码器组的名称完全匹配。请参阅<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML解码器组</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Source ID（日志源 ID） </td> 
   <td colname="col2"> <p>此字段的值可以是任意字符串。如果指定了某个值，则此字段可让您将来自不同日志源的日志条目区分开，以便进行源识别或目标处理。x-log-source-id 字段填充了用于识别每个日志条目的日志源的值。例如，如果您想要识别名为 XMLFile01 的日志文件源中的日志条目，则可以键入 <span class="filepath">from XMLFile01</span>，然后该字符串将会传递到该源中每个日志条目的 x-log-source-id 字段。 </p> <p> 有关x-log-source-id字段的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f">事件数据记录字段</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mask Pattern（掩码模式） </td> 
   <td colname="col2"> <p>具有单个捕获子模式的正则表达式，可提取用于识别一系列日志文件源的一致名称。仅考虑文件名。对于正则表达式匹配，不考虑路径和扩展名。如果您没有指定<span class="wintitle">掩码模式</span>，则系统会自动生成掩码。 </p> <p> 对于 <span class="filepath">Logs\010105server1.xml</span> 和 <span class="filepath">Logs\010105server2.xml</span> 文件，掩码模式将为 <code>[0-9]{6}(.*)</code>. 此模式从以上文件名中提取字符串“server1”或“server2”。 </p> <p> 请参阅 <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> 正则表达式</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursive（递归） </td> 
   <td colname="col2"> true 或 false。如果此参数设为 true，则系统会在“<span class="wintitle">日志路径</span>”中指定的每个路径的所有子目录中搜索与指定文件名或通配符模式匹配的文件。默认值为 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reject File（拒绝文件） </td> 
   <td colname="col2"> 包含的日志条目不符合解码器条件的文件路径和名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use Start/End Times（使用开始/结束时间） </td> 
   <td colname="col2"> <p>true 或 false。如果此参数设为 true，并且指定了“开始时间”或“结束时间”，则此日志源的所有文件名称必须以 ISO 格式 (YYYYMMDD) 的日期开头。假定每个文件都包含某一 GMT 日期（例如，时间范围从某一天的 0000 GMT 开始，到第二天的 0000 GMT 结束）的数据。如果日志源的文件名没有以 ISO 日期开头，或者文件包含的数据与 GMT 日期不对应，则此参数必须设为 false 才能避免产生错误结果。 </p> <p> <p>注意：如果 XML 文件满足上述命名和时间范围要求，并且您将此参数设为 true，则指定的 XML 解码器组会将读取的文件限制为名称中含有的 ISO 日期介于指定“开始时间”和“结束时间”之间的文件。如果您将此参数设为 false，则 Data Workbench Server 会在日志处理过程中读取所有 XML 文件，以确定哪些文件包含介于“开始时间”和“结束时间”之间的数据。 </p> </p> <p> 有关 Start Time（开始时间）和 End Time（结束时间）参数的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">数据过滤器</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>在定义数据集的数据源后，您不应删除或移动XML日志源。 只能将新创建的 XML 文件添加到数据源的目录中。

<!--
AVRO-log-file.xml
-->

通过 Avro 数据馈送，可以更有效地将数据集成到 Data Workbench：

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro 提供一种单源格式的流量和商务数据。
* Avro 馈送是压缩数据，包含每天提供的多源块。它仅设置填充的字段，并提供监测和通知功能、历史数据访问和自动恢复。
* 在每个文件开头都包含一个架构，也就是 Avro 日志文件的自定义布局。
* 添加了一些新字段，支持引入 Data Workbench 数据，无需对解码器进行任何更改。这些功能包括：

   * Evar：1-250（之前为 1-75）
   * 自定义事件：1-1000（而不是 1-100）
   * 访问移动、社交和视频数据的解决方案变量

>[!NOTE]
>
>此外，使用Avro源，可以在不关闭的情况下立即访问源中的任何新字段，从而无需服务小时要求即可更新这些字段。

可以在单独的文件中设置 Avro 数据馈送：

* **Avro 日志文件**：这是从解码器中生成的 Avro 日志格式，用于格式化流量和商务数据。
* **Avro 解码器文件**：此文件允许您将值映射为新的 Avro 格式。您可以使用“Avro 解码器向导”设置解码器。

## Avro 解码器向导  {#section-9a824b4c3d5549e7952a7111232035b2}

本向导可用于设置 Avro 解码器日志文件。

要打开向导，请右键单击工作区，然后选择&#x200B;**管理员** > **向导** > **Avro 解码器向导**。

**步骤 1：****选择一个 Avro 日志文件**。

在此步骤中，您可以为 Avro 架构选择一个源文件。可以通过日志文件 (.log) 或现有的解码器文件 (.avro) 访问架构。架构可从以下任一文件中提取。

| **Avro日志文件** | 单击打开一个日志 (.log) 文件，查看日志文件顶部的架构并生成解码器文件。 |
|---|---|
| **Avro 解码器文件** | 单击打开并编辑现有解码器 (.avro) 文件的架构。 |

**步骤 2：选择输入字段**。

选择用于在数据集中通过日志处理传输的输入字段。文件中的所有字段都将显示，便于您选择用于馈送的字段。

>[!NOTE]
>
>如果数据中遇到数组，则提供[!DNL x-product(Generates row)]字段。 此字段将为数组中的嵌套数据生成新行作为输入字段。例如，如果一个数组中有一个 Hit 行包含多个产品值，那么将在输入文件中为每个产品生成相应的行。

| **选择默认设置** | 选择要标识为标准默认字段集的字段。 |
|---|---|
| **选择全部** | 选择文件中的所有字段。 |
| **取消全选** | 清除文件中的所有字段。 |

**步骤 3：选择要复制来生成行的字段。**

由于可以从数组中的嵌套值创建新行，因此每个创建的新行都必须具有跟踪 ID 和时间戳。此步骤允许您从父记录中选择要复制到行的字段，例如跟踪 ID 和时间戳。您也可以选择想要添加到每行的其他值。

| **选择默认设置** | 选择需要向每行添加新列值的标准默认字段集，例如跟踪 ID 和时间戳。例如，[!DNL hit_source] 字段是需要添加到每个新行的默认值（在列表中定义为默认值）。您可以根据需要向每行添加其他列值。 |
|---|---|
| **选择全部** | 选择文件中的所有字段。 |
| **取消全选** | 清除文件中的所有字段。 |

使用&#x200B;**搜索**&#x200B;框可在列表中查找值。

**步骤 4：指定解码器名称**

为字段组指定一个名称，然后将其另存为解码器文件。该名称应与日志源中指定的解码器组名称相匹配。

**步骤 5：保存解码器文件。**

文件菜单将打开以命名解码器文件，并另存为&#x200B;**Logs**&#x200B;文件夹中的[!DNL .cfg]文件。
