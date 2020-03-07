---
description: Data Workbench Transform.cfg 文件包含用于定义日志源、数据转换和导出程序的参数。
solution: Analytics
title: Transform.cfg 文件
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Transform.cfg 文件{#the-transform-cfg-file}

Data Workbench Transform.cfg 文件包含用于定义日志源、数据转换和导出程序的参数。

The transformations that you define manipulate raw data collected by Sensors ( [!DNL .vsl] files) or contained in text files, XML files, or ODBC-compliant databases and output them either into existing fields, overwriting the current data, or into newly defined fields.

若要配置转换功能，需要在要导出事件数据的配置文件 Dataset 文件夹内编辑 Data Workbench [!DNL Transform.cfg] 文件。通常，此配置文件将专门用于转换功能（也就是说，除了 Data Workbench [!DNL Transform.cfg] 文件中定义的数据处理以外，不执行其他任何数据处理）。It is important to note that any processing instructions specified in the [!DNL Log Processing Dataset Include] files for any inherited profiles are applied in addition to those specified in the data workbench [!DNL Transform.cfg] file.

有关数据集包含文件的信息，请参阅 [数据集包含文件](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

如果您要导出的数据由 Data Workbench Server 群集处理，则群集中的每个处理服务器 (DPU) 都将处理数据，但只有第一个 DPU（[!DNL profile.cfg] 文件中的处理服务器 #0）会将输出数据写入其本地文件系统中。

**编辑 Data Workbench Transform.cfg 文件**

1. While working in the profile for which you want to export data, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show the contents of the directory.
1. Right-click the check mark next to data workbench [!DNL Transform.cfg], then click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 The data workbench [!DNL Transform.cfg] window appears.
1. 参考下表，编辑该配置文件中的参数：

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> 参数 </th> 
    <th colname="col2" class="entry"> 描述 </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> End Time（结束时间） </td> 
    <td colname="col2"> <p>可选。过滤数据以包含到此时间戳之前的日志条目，但不包含此时的日志条目。Adobe 建议使用以下时间格式之一： 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定“July 29 2013 00:00:00 EDT”作为“<span class="wintitle">结束时间</span>”，将包含截至 2013 年 7 月 28 日美国东部时间晚上 11:59:59 的数据。 </p> <p> 必须指定时区。如果未指定，时区不会默认为 GMT。有关 Data Workbench Server 支持的时区缩写列表，请参阅<a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">时区代码</a>。 </p> <p> 传感器和日志文件源的 Use Start/End Times（使用开始/结束时间）参数与此参数相关。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exporters（导出程序） </td> 
    <td colname="col2"> <p>导出程序的子字段指定如何处理输出数据和/或设置输出数据的格式。可以为一组日志源定义多个导出程序。每个导出程序类型都独立创建输出。 </p> <p> 存在以下三种类型的导出程序： 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> 有关导出程序类型的详细信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> 定义导出程序 </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hash Threshold（哈希阈值） </td> 
    <td colname="col2"> 可选。对行进行随机二次采样的采样因子。如果设为数字 n，则每 n 个跟踪 ID 中只会选择一个进行导出，从而使导出行的总数按系数 n 减少。若要导出所有行，您需要将 Hash Threshold（哈希阈值）设为 1。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Log Entry Condition（日志条目条件） </td> 
    <td colname="col2"> 可选。定义用于考虑导出日志条目的规则。有关日志条目条件的 <span class="wintitle"> 详细信息，请参 </span>阅日志 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 处理配置文件 </a>。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Log Sources（日志源） </td> 
    <td colname="col2"> <p>数据源。“<span class="wintitle">日志源</span>”可以是 <span class="filepath">.vsl</span> 文件、日志文件、XML 文件或 ODBC 兼容数据库中的数据。有关日志源的 <span class="wintitle"> 信息， </span>请参阅日志 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 处理配置文件 </a>。 </p> <p> <span class="wintitle">转换</span>认为所有源数据在按字典顺序排列的输入文件中都按年代顺序排列。如果不满足此要求，则无法正确计算“截至”时间，并且其他输入数据可能会在输出文件关闭之后才得到处理。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offline Mode（离线模式） </td> 
    <td colname="col2"> <p>可选。true 或 false。如果为 true，则<span class="wintitle">转换</span>假定在开始处理数据时，所有输入文件都存在。在读取所有输入数据之后，<span class="wintitle">转换</span>会关闭所有输出文件，而不等待接收更多数据。默认值为 false。 </p> <p> <p>注意：如果“<span class="wintitle">离线模式</span>”设为 true，则<span class="wintitle">转换</span>认为在处理开始之前，所有源数据都存在。如果在输出文件关闭之后收到其他数据，则 <span class="filepath">VisualServer.log</span> 文件中会生成一条警告消息。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Reprocess（重新处理） </td> 
    <td colname="col2"> <p>可选。此处可以输入任意字符或字符组合。更改此参数并将文件保存到<span class="wintitle">转换</span>计算机中，会开始重新处理数据。 </p> <p> 有关重新处理数据的信息，请参阅重新 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 处理和重新转换 </a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Stages（阶段） </td> 
    <td colname="col2"> <p>可选。可用在除 Data Workbench <span class="filepath">Transform.cfg</span> 文件之外执行的<span class="wintitle">日志处理数据集包含</span>文件中的处理阶段名称。处理阶段提供了一种对<span class="wintitle">日志处理数据集包含</span>文件中定义的转换进行排序的方式。如果您在多个<span class="wintitle">日志处理数据集包含</span>文件中定义了一个或多个转换，并且希望特定的转换在导出过程中的特定时间点执行，则此参数非常有用。 </span></p> <p> 您在此处列出阶段的顺序决定了在数据导出过程中对<span class="wintitle">日志处理数据集包含</span>文件中的转换执行的顺序。“<span class="wintitle">预处理</span>”和“<span class="wintitle">后处理</span>”都是内置阶段；“<span class="wintitle">预处理</span>”始终是第一个阶段，“<span class="wintitle">后处理</span>”始终是最后一个阶段。默认情况下，有一个称为“<span class="wintitle">默认</span>”的指定阶段。 </p> <p> <b>添加新处理阶段</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> 在 Data Workbench <span class="filepath">Transform.cfg</span> 窗口中，右键单击<span class="uicontrol">阶段</span>，然后单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">阶段</span>。 </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> 输入新阶段的名称。 </li> 
      </ul> <p> <b>删除现有处理阶段</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> 右键单击要删除的阶段所对应的编号，然后单击<span class="uicontrol">删除</span><i>&lt;<span class="uicontrol">阶段编号</span>&gt;</i>。 </li> 
      </ul> <p> <p>注意：当您在<span class="wintitle">日志处理数据集包含</span>文件中指定阶段时，该阶段的名称必须与您在此处输入的名称完全匹配。有关数据集包含文件的详细信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 数据集包含文件 </a>。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Start Time（开始时间） </td> 
    <td colname="col2"> <p>可选。过滤数据以包含具有此时或之后时间戳的日志条目。Adobe 建议使用以下时间格式之一： </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> <p> 例如，指定“July 29 2013 00:00:00 EDT”作为开始时间，将包含从 2013 年 7 月 29 日美国东部时间凌晨 12:00:00 开始的数据。 </p> <p> 必须指定时区。如果未指定，时区不会默认为 GMT。有关 Data Workbench Server 支持的时区缩写列表，请参阅<a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">时区代码</a>。 </p> <p> <p>注意：传感器和日志文件源的 Use Start/End Times（使用开始/结束时间）参数与此参数相关。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformations（转换） </td> 
    <td colname="col2"> <p>可选。定义要应用于数据的转换。有关可用转换类型的信息，请参阅<a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md">数据转换</a>。 </p> <p> <p>注意：以下转换类型在 Data Workbench <span class="filepath">Transform.cfg</span> 文件中定义时将无法正常使用： </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>If additional data is received after the output files are closed (see [!DNL Log Sources] and [!DNL Offline Mode] in the preceding table), [!DNL Transform] creates new output files with the additional data. 新输出文件的名称生成自原始输出文件的名称（在紧靠扩展名的前面添加带括号的版本号）。For example, if the original output file is [!DNL 20070701-ABC.vsl], subsequent versions of this file will be named [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl], and so on. 请注意，将版本控制的文件用作 Data Workbench Server 的输入，可能会导致处理错误。
>
>
>Adobe 建议确保所有源数据在按字典顺序排列的输入文件中都按年代顺序排列，以及当 [!DNL Offline Mode]（离线模式）设为 true 时，确保所有源数据在处理开始之前都存在，从而避免创建版本控制的输出文件。For more information, see the [!DNL Log Sources] and [!DNL Offline Mode] entries in the preceding table.

1. 通过右键单击并单击 **[!UICONTROL Transformations]** >添加 **[!UICONTROL Add new]** 转换 **[!UICONTROL Transformation type]**。 完成转换字段。

   See [Data Transformations](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) for descriptions and examples of the transformations that you can use with transformation functionality.

1. Right-click **[!UICONTROL (modified)]** at the top of the window, then click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for data workbench [!DNL Transform.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, where profile name is the name of the profile for which you are exporting data. 在配置文件同步之后，系统便会开始重新处理数据。

   >[!NOTE]
   >
   >有关重新处理数据以便导出的信息，请参阅重新 [处理和重新转换](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
