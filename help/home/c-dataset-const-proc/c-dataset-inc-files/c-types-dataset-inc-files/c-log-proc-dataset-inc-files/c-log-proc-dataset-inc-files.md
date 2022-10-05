---
description: 继承配置文件的日志处理数据集包含文件中含有与数据集构建的日志处理阶段相关的参数。
title: 日志处理数据集包含文件
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 76%

---

# 日志处理数据集包含文件{#log-processing-dataset-include-files}

{{eol}}

继承配置文件的日志处理数据集包含文件中含有与数据集构建的日志处理阶段相关的参数。

的第一行 [!DNL Log Processing Dataset Include] 文件定义类型 [!DNL LogProcessingInclude] 支持解码器组、字段、日志条目条件、参数、重新处理、暂存和转换参数。 日志处理的其他所有参数都必须在数据集配置文件 Dataset 目录的 [!DNL Log Processing.cfg] 文件中定义。您可以将 [!DNL Log Processing Dataset Include] 需要的任何文件，但其文件扩展名必须为 [!DNL .cfg]. 文件必须存储在&#x200B;*继承配置文件名称*\Dataset\Log Processing 目录中。由于文件是在数据集构建的日志处理阶段递归加载的，因此您可以存储 [!DNL Log Processing Dataset Include] 目录中任何级别的文件(例如， *继承配置文件名称*\Dataset\Log Processing\*文件夹名称*\*包含文件名*.cfg)。

>[!NOTE]
>
>Site的许多特定于Web的配置参数在 [!DNL Log Processing Dataset Include] 文件。 有关这些参数的信息，请参阅 [Web数据的配置设置](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Decoder Groups（解码器组） </td> 
   <td colname="col2"> <p>如果您在 <span class="filepath">Log Processing.cfg</span> 文件中定义了日志文件或 XML 文件日志源，则需要此参数。此参数是您定义的文本文件或 XML 解码器，用于从日志文件和 XML 日志源中提取数据字段。 </p> <p> <b>添加新解码器组</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> 右键单击<span class="uicontrol">解码器组</span>，然后单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">TextFileDecoderGroup</span> 或 <span class="uicontrol">XMLDecoderGroup</span>。 </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> 在新组的 Name（名称）参数中，输入所需的解码器组名称。 </li> 
     </ul> </p> <p> <p>注意：当您在数据集配置文件的 <span class="filepath">Log Processing.cfg</span> 文件中指定解码器组时，其名称必须与您在此处输入的名称完全匹配。有关更多信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> 日志文件</a>. </p> </p> <p> 有关可为每个组定义的解码器的信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> 文本文件解码器组</a> 或 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML解码器组</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 字段 </td> 
   <td colname="col2"> <p>此处必须列出在<span class="wintitle">日志处理数据集配置</span>文件的<span class="wintitle">日志源</span>或<span class="wintitle">转换</span>中定义，但用于<span class="wintitle">转换数据集配置</span>文件中的转换、条件或扩展维度的列表字段。 </p> <p> 以下每个字段都必须列在某些<span class="wintitle">日志处理数据集包含</span>文件中： 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Entry Condition（日志条目条件） </td> 
   <td colname="col2"> <p>可选。定义用于考虑将日志条目加入数据集中的规则。请参阅 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 日志条目条件</a>. </p> <p> <p>注意：若要将某个日志条目包含在数据集中，该条目必须满足 <span class="wintitle">Log Processing.cfg</span> 文件和每个<span class="filepath">日志处理数据集包含</span>文件中的<span class="wintitle">日志条目条件</span>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参数 </td> 
   <td colname="col2"> 可选。您可以在其他配置参数中引用的变量。有关详细信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 在数据集包含文件中定义参数</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess（重新处理） </td> 
   <td colname="col2"> <p>可选。此处可以输入任意字符或字符组合。更改此参数并将文件保存到 Data Workbench Server，会开始重新处理数据。 </p> <p> 有关重新处理数据的信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新处理和重新转换</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage（阶段） </td> 
   <td colname="col2"> <p>可选。应用于此<span class="wintitle">日志处理数据集包含</span>文件的处理阶段名称。处理阶段在 <span class="filepath">Log Processing.cfg</span> 文件的 Stage（阶段）参数中定义。 </p> <p> <p>注意：当您指定阶段时，阶段的名称必须与数据集配置文件的 <span class="filepath">Log Processing.cfg</span> 文件中 Stage（阶段）参数所列的名称完全匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations（转换） </td> 
   <td colname="col2"> 可选。定义需要在日志处理过程中应用的数据转换。有关可用转换类型的信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 数据转换</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有关 [!DNL Log Processing.cfg] 文件，请参阅 [日志处理配置文件](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

每当您使用 [!DNL Log Processing Dataset Include] 文件：

* 更改此文件中的任何参数都需要重新处理所有数据。
* 您可以将上述任何参数添加到 [!DNL Log Processing Dataset Include] 文件中，只需在记事本中打开并编辑该文件即可。当您在 Data Workbench 中重新打开该文件时，系统便会显示您做出并保存的所有更改。在添加新参数时，使用空格键（而不是 Tab 键）可向上一个标题级别的右侧缩进两 (2) 个空格。
