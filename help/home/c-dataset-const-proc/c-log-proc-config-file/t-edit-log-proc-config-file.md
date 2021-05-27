---
description: 编辑数据集配置文件的 Log Processing.cfg 文件的步骤。
title: 编辑日志处理配置文件
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 80%

---

# 编辑日志处理配置文件{#editing-the-log-processing-configuration-file}

编辑数据集配置文件的 Log Processing.cfg 文件的步骤。

1. 在处理数据集配置文件时，打开[!DNL Profile Manager]并单击&#x200B;**[!UICONTROL Dataset]**&#x200B;以显示其内容。

   有关打开和使用[!DNL Profile Manager]的信息，请参阅&#x200B;*Data Workbench用户指南*。

   >[!NOTE]
   >
   >日志处理子目录可能位于Dataset目录内。 此子目录包含为一个或多个继承配置文件创建的[!DNL Log Processing Dataset Include]文件。 请参阅[数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 右键单击[!DNL Log Processing.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。
1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。 出现[!DNL Log Processing.cfg]窗口。

   您还可以从[!DNL Transformation Dependency Map]打开[!DNL Log Processing.cfg]文件。 有关转换依赖关系图的信息，请参阅[数据集配置工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

1. 参考下表，编辑该配置文件中的参数。

   在 Data Workbench 窗口内编辑 [!DNL Log Processing.cfg] 文件时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。您还可以使用快捷方式将文本从一个配置文件([!DNL .cfg])复制并粘贴到另一个配置文件。

   >[!NOTE]
   >
   >继承配置文件的[!DNL Log Processing Dataset Include]文件包含下表中描述的参数子集以及一些其他参数。 请参阅[数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 参数 </th> 
      <th colname="col2" class="entry"> 描述 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 日志源 </td> 
      <td colname="col2"> 数据源。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea">日志源</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> End Time（结束时间） </td> 
      <td colname="col2"> <p>可选。过滤数据以包含到此时间戳之前的日志条目，但不包含此时的日志条目。Adobe 建议使用以下时间格式之一： </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">January 1 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> <p>例如，指定“July 29 2013 00:00:00 EDT”作为结束时间，将包含截至 2013 年 7 月 28 日美国东部时间晚上 11:59:59 的数据。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">数据过滤器</a>。 </p> <p>必须指定时区。如果未指定，时区不会默认为 GMT。有关 Data Workbench Server 支持的时区缩写列表，请参阅 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 时区代码 </a>. </p> <p> <p>注意：<span class="wintitle">传感器</span>、日志文件和 XML 源的 Use Start/End Times（使用开始/结束时间）参数与此参数相关。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea">日志源</a>中讨论这些源类型的部分。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fields（字段） </td> 
      <td colname="col2"> 可选。Adobe 建议在一个或多个<span class="wintitle">日志处理数据集包含</span>文件中定义 <span class="wintitle">Fields</span>（字段）。请参阅<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab">日志处理数据集包含文件</a> 。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Group Maximum Key Bytes（组最大键字节数） </td> 
      <td colname="col2"> <p>服务器可为单个跟踪 ID 处理的最大事件数据量。超过此限制的数据会被数据集构建过程过滤出去。当键拆分处于活动状态时，此值必须设为 2e6；当键拆分处于不活动状态时，此值必须设为 1e6。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">键拆分</a>。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，请勿更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash Threshold（哈希阈值） </td> 
      <td colname="col2"> <p>可选。对行进行随机二次采样的采样因子。如果设置为数字 n，那么每 n 个跟踪 ID 中只有一个会进入数据集，从而将数据集中的总行数减少到原来的 1/n。 </p> <p>要创建需要 100% 准确度（即包括所有行）的数据集，您需要将 Hash Threshold（哈希阈值）设置为 1。 </p> <p>值： </p> <span class="filepath">Hash Threshold = 1</span>（100% 的数据，包含所有行。） <p> <span class="filepath">Hash Threshold = 2</span>（1/2 的数据，包含一半的行。） </p> <p> <span class="filepath">Hash Threshold = 3 </span>（1/3 的数据，包含三分之一的行，但在“查询完成”中会四舍五入为 34%。） </p> <p> <span class="filepath">Hash Threshold = 4 </span>（1/4 的数据，包含四分之一的行。） </p> <p> </p> <p> <p>注意：如果使用 <span class="filepath">Hash Threshold = 8</span>，那么会提供 1/8 的数据，即 12.5%。但<span class="uicontrol">查询完成</span>值会将此值四舍五入为 13%。其他示例包括 <span class="filepath">Hash Threshold = 6</span>，此值将提供 17% 的查询结果。<span class="filepath">Hash Threshold = 13 </span>将提供 8% 的查询结果。 </p> </p> <p>如果 <span class="filepath">Log Processing.cfg</span> 和 <span class="filepath">Transformation.cfg</span> 文件中都指定了 <span class="wintitle">Hash Threshold</span>（哈希阈值），则该参数不会按顺序应用，而是会应用两个配置文件中设置最大的那个值。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">数据过滤器</a>。 </span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Log Entry Condition（日志条目条件） </td> 
      <td colname="col2"> 可选。定义用于考虑将日志条目加入数据集中的规则。请参阅 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 日志条目条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocess（重新处理） </td> 
      <td colname="col2"> <p>可选。此处可以输入任意字符或字符组合。更改此参数并将文件保存到 Data Workbench Server 计算机中，会开始重新处理数据。 </p> <p>请参阅 <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新处理和重新转换 </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bucket Space（拆分键存储段空间） </td> 
      <td colname="col2"> <p>键拆分中涉及的参数。当键拆分处于活动状态时，其值应该为 6e6。请参阅<a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split">键拆分</a>。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，请勿更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bytes（拆分键字节数） </td> 
      <td colname="col2"> <p>键拆分中涉及的参数。当键拆分处于活动状态时，其值应该为 1e6；当键拆分处于不活动状态时，其值应该为 0。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">键拆分</a>。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，请勿更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Space Ratio（拆分键空间比率） </td> 
      <td colname="col2"> <p>键拆分中涉及的参数。当键拆分处于活动状态时，其值应该为 10。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">键拆分</a>。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，请勿更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stages（阶段） </td> 
      <td colname="col2"> <p>可选。可以在<span class="wintitle">日志处理数据集包含</span>文件中使用的处理阶段的名称。处理阶段提供了一种对<span class="wintitle">日志处理数据集包含</span>文件中定义的转换进行排序的方式。如果您在多个<span class="wintitle">日志处理数据集包含</span>文件内定义了一个或多个转换，并且您希望特定的转换在日志处理过程中的特定时间点执行，则此参数非常有用。 </p> <p>您在此处列出阶段的顺序决定了在日志处理过程中对<span class="wintitle">日志处理数据集包含</span>文件中的转换执行的顺序。“预处理”和“后处理”都是内置阶段；“预处理”始终是第一个阶段，“后处理”始终是最后一个阶段。默认情况下，有一个称为“默认”的指定阶段。 </p> <p> <b>添加新处理阶段</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">在 <span class="filepath">Log Processing.cfg</span> 窗口中，右键单击<span class="uicontrol">阶段</span>，然后单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">阶段</span>。 </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">输入新阶段的名称。 </li> 
      </ul> </p> <p> <b>删除现有处理阶段</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">右键单击要删除的阶段所对应的编号，然后单击<span class="uicontrol">删除</span><i>&lt;<span class="uicontrol">阶段编号</span>&gt;</i>。 </li> 
      </ul> </p> <p> <p>注意：当您在<span class="wintitle">日志处理数据集包含</span>文件中指定<span class="wintitle">阶段</span>时，该阶段的名称必须与您在此处输入的名称完全匹配。请参阅<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md">数据集包含文件</a> 。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Start Time（开始时间） </td> 
      <td colname="col2"> <p>可选。过滤数据以包含具有此时或之后时间戳的日志条目。Adobe 建议使用以下时间格式之一： </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 2013年1月1日HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定“July 29 2013 00:00:00 EDT”作为开始时间，将包含从 2013 年 7 月 29 日美国东部时间凌晨 12:00:00 开始的数据。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">数据过滤器</a>。 </p> <p> 必须指定时区。如果未指定，时区不会默认为 GMT。有关 Data Workbench Server 支持的时区缩写列表，请参阅 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 时区代码 </a>. </p> <p> <p>注意：<span class="wintitle">传感器</span>、日志文件和 XML 源的 Use Start/End Times（使用开始/结束时间）参数与此参数相关。请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea">日志源</a>中讨论这些源类型的部分。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 时区 </td> 
      <td colname="col2"> <p>可选。Data Workbench Server的时区，用于在日志处理期间进行时间转换（例如由x-local-timestring字段表示的转换）。 </p> <p> <p>注意：如果您想要在数据集构建的日志处理阶段访问已转换的时间字段，则必须指定时区。否则，Data Workbench Server 会在事件日志中记录一条错误。 </p> </p> <p>请参阅 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 时区 </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations（转换） </td> 
      <td colname="col2"> 可选。Adobe 建议在一个或多个<span class="wintitle">日志处理数据集包含</span>文件中为日志处理定义转换。请参阅<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab">日志处理数据集包含文件</a> 。 </td> 
   </tr> 
   </tbody> 
   </table>

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL Log Processing.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]**>*&#x200B;以使本地所做的更改生效。 在数据集配置文件同步之后，系统便会开始重新处理数据。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

   有关重新处理数据的更多信息，请参阅[重新处理和重新转换](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
