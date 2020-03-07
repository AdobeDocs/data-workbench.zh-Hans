---
description: 编辑数据集配置文件的 Transformation.cfg 文件的步骤。
solution: Analytics
title: 编辑转换配置文件
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 编辑转换配置文件{#editing-the-transformation-configuration-file}

编辑数据集配置文件的 Transformation.cfg 文件的步骤。

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.

   For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*.

   >[!NOTE]
   >
   >Transformation子目录可能存在于Dataset目录中。 This subdirectory contains the [!DNL Transformation Dataset Include] files that have been created for one or more inherited profiles. 有关文件的 [!DNL Transformation Dataset Include] 信息，请参阅 [数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 右键单击旁边的复选标记， [!DNL Transformation.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。 The [!DNL Transformation.cfg] window appears.

   您还可以从 [!DNL Transformation.cfg] 打开文件 [!DNL Transformation Dependency Map]。 有关信息，请 [!DNL transformation dependency maps]参阅数 [据集配置工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

1. 参考下表，编辑该配置文件中的参数。

   在 Data Workbench 窗口内编辑 [!DNL Transformation.cfg] 文件时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] files for an inherited profile contains a subset of the parameters described in the following table as well as some additional parameters. 有关文件的信 [!DNL Transformation Dataset Include] 息，请参阅数 [据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
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
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定“July 29 2013 00:00:00 EDT”作为结束时间，将包含截至 2013 年 7 月 28 日美国东部时间晚上 11:59:59 的数据。 </p> <p> 必须指定时区。如果未指定，时区不会默认为 GMT。有关 Data Workbench Server 支持的时区缩写列表，请参阅<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">时区代码</a>。 </p> <p> <p>注意：如果为结束时间指定了一个值，则系统会设置一个名为 End Time（结束时间）的参数，并在数据集构建的整个转换阶段应用该参数。有关参数的信息，请参阅在数 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 据集包含文件中定义参数 </a>。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Extended Dimensions（扩展维度） </td> 
      <td colname="col2"> 可选。Adobe 建议在一个或多个<span class="wintitle">转换数据集包含</span>文件中定义扩展维度。有关信息，请参阅转 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 换数据集包含文 </a>件。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash Threshold（哈希阈值） </td> 
      <td colname="col2"> <p>可选。对行进行随机二次采样的采样因子。如果设为数字 n，则每 n 个跟踪 ID 中只有一个会进入数据集，使数据集中的总行数按系数 n 减少。若要创建要求 100% 准确度（即包含所有行）的数据集，您需要将 Hash Threshold（哈希阈值）设为 1。 </p> <p> 如果 <span class="filepath">Log Processing.cfg</span> 和 <span class="filepath">Transformation.cfg</span> 这两个文件中都指定了 Hash Threshold（哈希阈值），则该参数不会按顺序应用；而是会应用两个配置文件中设置最大的那个值。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Log Entry Condition（日志条目条件） </td> 
      <td colname="col2"> 可选。定义用于考虑将日志处理过程中输出的日志条目加入数据集配置文件中的规则。请参阅 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 日志条目条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> New Visitor Condition（新访客条件） </td> 
      <td colname="col2"> 可选。与 Web 数据一起使用。定义用于考虑将访客加入数据中的规则。<span class="wintitle">New Visitor Condition</span>（新访客条件）为要用在数据集中的访客定义第一个日志条目（按时间排序）。此访客的所有后续日志条目都会包含在数据集中，无论这些条目是否符合此条件。请参阅 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> 新访客条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocess（重新处理） </td> 
      <td colname="col2"> <p>可选。此处可以输入任意字符或字符组合。更改此参数并保存文件会开始重新转换数据。 </p> <p> 有关重新处理数据的信息，请参阅<a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">重新处理和重新转换</a>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schema Checking（架构检查） </td> 
      <td colname="col2"> true 或 false。如果为 true，则 Data Workbench Server 会识别数据集损坏问题，并在 Data Workbench Server 的 Trace 目录的日志文件中，记录与这些问题有关的信息。默认值为 true。Adobe 建议始终将此参数设为 true。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stages（阶段） </td> 
      <td colname="col2"> <p>可选。可以在<span class="wintitle">转换数据集包含</span>文件中使用的处理阶段的名称。处理阶段提供了一种对<span class="wintitle">转换数据集包含</span>文件中定义的转换进行排序的方式。如果您在多个<span class="wintitle">转换数据集包含</span>文件内定义了一个或多个转换，并且您希望特定的转换在转换过程中的特定时间点执行，则此参数非常有用。 </p> <p> 您在此处列出阶段的顺序决定了在转换过程中对<span class="wintitle">转换数据集包含</span>文件中的转换执行的顺序。“<span class="wintitle">预处理</span>”和“<span class="wintitle">后处理</span>”都是内置阶段；“<span class="wintitle">预处理</span>”始终是第一个阶段，“<span class="wintitle">后处理</span>”始终是最后一个阶段。默认情况下，有一个称为“<span class="wintitle">默认</span>”的指定阶段。 </p> <p> <b>添加新处理阶段</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> 在 <span class="filepath">Transformation.cfg</span> 窗口中，右键单击<span class="uicontrol">阶段</span>，然后单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">阶段</span>。 </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> 输入新阶段的名称。 </li> 
      </ul> </p> <p> <b>删除现有处理阶段</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> 右键单击要删除的阶段所对应的编号，然后单击<span class="uicontrol">删除</span><i>&lt;<span class="uicontrol">阶段编号</span>&gt;</i>。 </li> 
      </ul> </p> <p> <p>注意：当您在<span class="wintitle">转换数据集包含</span>文件中指定阶段时，该阶段的名称必须与您在此处输入的名称完全匹配。有关数据集包含文件的详细信息，请参阅 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 数据集包含文件 </a>。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Start Time（开始时间） </td> 
      <td colname="col2"> <p>可选。过滤数据以包含具有此时或之后时间戳的日志条目。Adobe 建议使用以下时间格式之一： 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定“July 29 2013 00:00:00 EDT”作为“<span class="wintitle">开始时间</span>”，将包含从 2013 年 7 月 29 日美国东部时间凌晨 12:00:00 开始的数据。 </p> <p> 必须指定时区。如果未指定，时区不会默认为 GMT。有关 Data Workbench Server 支持的时区缩写列表，请参阅<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">时区代码</a>。 </p> <p> <p>注意：如果为“开始时间”指定一个值，则系统会设置一个名为“开始时间”的参数，并在数据集构建的整个转换阶段应用该参数。有关参数的信息，请参阅在数 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 据集包含文件中定义参数 </a>。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations（转换） </td> 
      <td colname="col2"> 可选。Adobe 建议在一个或多个<span class="wintitle">转换数据集包含</span>文件中为数据集构建的转换阶段定义转换。有关信息，请参阅转 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 换数据集包含文 </a>件。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 时区 </td> 
      <td colname="col2"> <p>数据集配置文件的时区。时区用于进行时间转换和创建时间维度。请参阅 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 时区 </a>. </p> <p> <p>注意：在 <span class="filepath">Log Processing.cfg</span> 文件中定义 Time Zone（时区）参数时，该参数仅用于进行时间转换。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
1. 在列 [!DNL Profile Manager]中，右键单击列中的复 [!DNL Transformation.cfg]选 [!DNL User] 标记，然后单击 **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** 以使本地所做的更改生效。 在数据集配置文件同步之后，系统便会开始重新转换数据。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

   有关重新处理或重新转换数据的信息，请参阅重新 [处理和重新转换](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
