---
description: 有关Report.cfg参数的信息。
solution: Analytics
title: Report.cfg参数
topic: Data workbench
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Report.cfg参数{#report-cfg-parameters}

有关Report.cfg参数的信息。

默认情 [!DNL Report.cfg] 况下，配 [置报告集中显示的示例仅包含文件中](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)[!DNL Report.cfg] 包含的参数。 下表提供所有可用文件参数的 [!DNL Report.cfg] 说明。

如果需要向文件添加其他参 [!DNL Report.cfg] 数，则必须使用文本编辑器。 要执行此操作的步骤（包括如何定义每个参数条目的示例），请参 [阅编辑现有Report.cfg文件](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)。

>[!NOTE]
>
>此表中的参数按字母顺序列出。 在Data Workbench中打开文 [!DNL Report.cfg] 件时，矢量按字母顺序列出，后跟按字母顺序列出的各个参数。

<table id="table_F55E925EA34F43B6832788BB6878BB4A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 警报阈值 </td> 
   <td colname="col2"> <p><i>可选</i>. 此参数仅适用于具有度量指示器的报表。 在发送警报报告之前，必须在工作表中显示的度量指标数。 </p> <p>如果在度量指示符工作表中只监视一个度量，请将阈值设置为1。 当工作表中的度量计算结果为向上／向下箭头或X时，将生成报告。如果报表中监视了多个度量，则可以选择度量指示符的数量，这些指标在生成报表之前必须计算为向上／向下箭头或X。 例如，如果监视两个度量： 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">如果阈值设置为1，则当工作表中的任一度量值为向上／向下箭头或X时，将生成报表。 </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">如果阈值设置为2，则生成报告前，这两个度量必须计算为向上／向下箭头或X。 </li> 
     </ul> </p> <p>For more information about metric indicators, see the <i>Data Workbench User Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 允许报告重新生成 </td> 
   <td colname="col2"> <p>指示在您创 <span class="keyword"> 建或修 </span> 改这些报告时，报告服务器是自动生成还是重新生成特定报告。 选项为 true 或 false。如果设置为true，则创建或修改报表工作区会导致 <span class="keyword"> Report Server </span> 为最近运行重新生成该报表。 </p> <p> <p>注意： 更改 <span class="filepath"> Report.cfg文件 </span> 会导致 <span class="keyword"> Report Server重新生成由该 </span> Report.cfg文件控制的所有 <span class="filepath"></span> 报告。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 附件 </td> 
   <td colname="col2"> <p><i>可选</i>. 通过电子邮件分发的报表导出的任何附件的名称和内容类型的章节标识符，包括附件数。 </p> <p>要添加新附件，请执行以下操作： 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">在Data Workbench <span class="filepath"> 中打开Report. </span> cfg文件。 </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">右键单击“附 <span class="uicontrol"> 件” </span> ，然后单 <span class="uicontrol"> 击“添加新子项” </span> &gt;“ <span class="uicontrol"> 附件” </span>。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 内容类型 </td> 
   <td colname="col2"> <p>要附加的文件的内容类型。 </p> <p>示例：image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 文件名 </td> 
   <td colname="col2"> <p>要附加的文件的位置和名称。 </p> <p>示例： <span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color Set（颜色集） </td> 
   <td colname="col2"> 标识要用于。png文件的 <span class="filepath"> 颜色方 </span> 案。 0表示黑色背景；1表示白色背景；2表示灰度图像。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 执行命令 </td> 
   <td colname="col2"> <i>可选</i>. 生成报告集后运行的批处理命令或可执行文件。 如果需要启动命令shell解释器，请在命令前面添加cmd /c。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 默认Excel模板 </td> 
   <td colname="col2"> <p><i>可选</i>. 将报表生成为Excel文件时要使用的通用Excel模板文件( <span class="filepath"> .xls </span> 或 <span class="filepath"> .xlsx </span>)的文件名。 此参数支持完整文件路径，如 <span class="filepath"> c:\templates\mytemplate.xls </span>。 </p> <p>除非为特定报表专门定义了模板，否则此文件将用于所有Excel报表。 请参 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> 阅使用模板文件 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维度名称 </td> 
   <td colname="col2"> <i>可选</i>. 要动态生成报表的维的名称。 如果在此参数中输入维名称，则必须在“查找文件”参数或“前N个度量”和“前N个值”参数中输入值。 在此参数中命名的维必须存在于为其创建报表的数据集中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 仅在完美时通过电子邮件发送 </td> 
   <td colname="col2"> <i>可选</i>. 允许用户指定仅在运行期间未发生错误时才发送报表集。 选项为 true 和 false。默认值为 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 结束日期 </td> 
   <td colname="col2"> <p><i>可选</i>. 您希望报表集运行的上次日期和时间。 此时间基于数据集的截止时间。 </p> <p>格式：MM/DD/YYYY hh:mm时区，使用时间为24小时的语法 </p> <p>示例：08/01/2007 12:01 EDT </p> <p>有关时区设置的详细信息，请参阅《数据集配置指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每个 </td> 
   <td colname="col2"> 生成报告集的频率：日、周或月。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excel监视程序超时（秒） </td> 
   <td colname="col2"> <p><i>可选</i>. 在报表服务器确定Excel未响应并终止该过程之前，您希望 <span class="keyword"> Report Server </span><span class="keyword"></span> 在将报表生成为Excel文件时等待Microsoft Excel响应的秒数。 使用此参数， <span class="keyword"> Report Server可 </span> 在Excel无响应时终止Excel并继续处理非Excel报表。 默认值为300.0。要禁用此功能，请将此参数设置为0.0。 </p> <p>确保您定义的值足够长，以允许将报表导出到Excel。 否则， <span class="keyword"> 报表服 </span> 务器可能会过早终止Excel，而您的报表将不会生成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 滤镜公式 </td> 
   <td colname="col2"> <p><i>可选</i>. 应用于报表集中每个工作区的过滤器。 </p> <p>有关详细信息，请参阅 <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> 创建过滤器的语法 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma校正 </td> 
   <td colname="col2"> <p>.png文件输 <span class="filepath"> 出的Gamma </span> 设置。 默认值为 1.6。 </p> <p> <p>注意： Adobe建议您不要更改此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隐藏徽标 </td> 
   <td colname="col2"> 指示在生成报表时，报表服务器是否隐藏徽标。 The options are <span class="filepath"> true </span> or <span class="filepath"> false </span>. 如果设置为 <span class="filepath"> false，则 </span>会使用“报告”徽标生成报告。 The default is <span class="filepath"> false </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查找文件 </td> 
   <td colname="col2"> <p><i>可选</i>. 填充此参数后，Report Server以动态模式运行，并为在Dimension Name（维名称）参数中指定的维的每个元素生成报表。 此文件必须包含两个制表符分隔的列，不含标题行。 </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">第1列包含维元素列表。 </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">第2列包含报告收件人的电子邮件地址。 第1列中给定元素的报告将发送到第2列中同一行的电子邮件地址。 您可以通过用逗号（无空格）分隔多个电子邮件地址来输入它们。 如果不要通过电子邮件发送报告，则此列可为空，但必须存在。 </li> 
     </ul> </p> <p> <p>注意： 如果在此参数中输入值，则必须在“维名称”(Dimension Name)参数中输入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 仅通知 </td> 
   <td colname="col2"> 此报 <span class="wintitle"> 表服务器 </span> 设置允许您配置Data Workbench，以在生成报表时发送电子邮件。 将此值设置为 <span class="filepath"> true不 </span> 会发出报告，而是发送电子邮件，通知订阅用户报告已生成。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 邮件报告 </td> 
   <td colname="col2"> <p>用于通过电子邮件分发报告的章节标识符。 要通过电子邮件分发报告，请完成“邮件报告”条目的 <span class="wintitle"> 以下 </span> 参数。 报告集中的所有报告都通过电子邮件发送到在“收件人”参数中指定的电子邮件地址。 </p> <p> <p>注意： 仅当报告服务器生成至少一个报告时，它才会发送电子邮件。 </p> </p> <p>要启用报告的电子邮件发送，您必须至少为此条目完成以下参数： 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP服务器 </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">收件人 </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">发件人地址 </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">仅通知 </li> 
     </ul> </p> <p> <p>注意： 要在重新生成报表集后通过电子邮件发送报表，请参阅编 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> 辑现有Report.cfg文件 </a>。 </p> </p> <p>“仅通知”值在5.4x和5.5x发行版中可用。 </p> <p>对于要通知的大量收件人（超过20个），强烈建议您使用电子邮件分发列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 正文XSL模板 </td> 
   <td colname="col2"> <p><i>可选</i>. 要应用于reports.xml文件的XSL模 <span class="filepath"> 板文件的路 </span> 径。 使用此参数，报表服务器可以在分布式电子邮件中而不是作为附件发送您的报表。 生成的文本将用作电子邮件正文。 </p> <p>有关 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> 示例文件，请参 </a> 阅报告示例文件。 </p> <p>有关可扩展样式表语言(XSLT)的信息，请参 <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> 阅可扩展样式表语言系列 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收件人 </td> 
   <td colname="col2"> 要向其发送报告的人员的电子邮件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发件人地址 </td> 
   <td colname="col2"> 发件人的电子邮件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发件人姓名 </td> 
   <td colname="col2"> 可选。发送方的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP服务器 </td> 
   <td colname="col2"> SMTP服务器计算机的地址以及身份验证所需的口令和用户名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主题 </td> 
   <td colname="col2"> <i>可选</i>. 描述要发送的电子邮件的主题行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 仅通知 </td> 
   <td colname="col2"> 允许您配置Data Workbench，以在生成后台报告时发送电子邮件。 将此值设置为True不会发出报表，而是发送一封电子邮件，将订阅用户链接到报表位置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 输出根 </td> 
   <td colname="col2"> <p><i>可选</i>. 生成的报告集的输出位置。 默认为Report Server安 <i>装目录中的</i>&lt;profile name&gt;\Reports文件夹。 </p> <p>要将报 <span class="keyword"> 告服务器配 </span> 置为将报告输出到门户，请将“输出根”设置 <span class="wintitle"></span> 为用于门户的Web服务器的文档根。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 预载查询过滤器 </td> 
   <td colname="col2"> <p><i>可选</i>. 此参数仅适用于“顶 <span class="wintitle"> 级维元素”报 </span> 告类型。 </p> <p>要应用到查询的过滤器的名称，必须运行该名称才能确定前N个维元素，然后才能生成报告。 默认值为 <span class="wintitle"> Broken_Session_Filter </span>。 For more information about the <span class="wintitle"> Broken Session Filter </span>, see the <i>Data Workbench User Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 报表类型 </span> </td> 
   <td colname="col2"> <p>要生成输出的格式。 您可以使用以下任意或所有选项一次以多种格式输出报表集： 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel会创建一个Excel工作簿，每个工作表有一个可视化视图。 通常，使用Excel文件进行电子邮件分发。 请参 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> 阅将报表生成为Microsoft Excel文件 </a>。 有关使用模板文件的信息，请参阅 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> 使用模板文件 </a>。 </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png创建可移植网络图形文件。 通常，使用。png文 <span class="filepath"> 件 </span> 在Web浏览器（门户）中显示。 </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">缩览图可创建工作区 <span class="filepath"> 的缩 </span> 览图（.jpg文件）。 默认大小为240x180。 要更改默认大小，请编辑Thumbnail X和Thumbnail Y参数。 </li> 
     </ul> </p> <p>要在Data Workbench中编辑 <span class="filepath"> Report.cfg时添加新的报表类型，请右键单击 </span> “报表类型” <span class="uicontrol"> ，单击 </span>“添加新子项” <span class="uicontrol"></span>，然后选择所需的报表类型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 开始日期 </td> 
   <td colname="col2"> <p>您希望报表集运行的第一个日期和时间。 此时间基于数据集的截止时间。 </p> <p>格式：MM/DD/YYY hh:mm时区，使用24小时的时间语法。 </p> <p>有关时区设置的详细信息，请参阅《数据集配置指南》<i></i>。 </p> <p> <p>注意： 当配置文件中数据的时间戳与指定的日期和时间匹配时，报表开始运行。 </p> </p> <p>示例： </p> <p>如果开始日期是08/08/2006 12:00 EST，则报表会为时间戳为08/08/2006 12:00 EST及更高版本的数据运行。 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">2006年8月08日和之后每天为hh:mm = 12:00的数据运行每日报告。 </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">每周报告将于2006年8月08日运行，其后每7天为hh:mm = 12:00的数据运行一次。 </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">月度报告将于2006年8月运行，其后每月的第8天运行，其中hh:mm = 12:00 EST。 </li> 
     </ul> </p> <p>“报 <span class="wintitle"> 告时间 </span> ”量度影响“最近N”报告维度，如“最近7天”、“昨天”和“3周前”。对于报告服务器中的查询， <span class="wintitle"> 报告时间 </span> 度量( <span class="filepath"> Report Time.metric </span>)可标识运行报告的日期和时间。 这最初是在“开始日期”参数中指定的日期和时间，然后按“每个”参数指定的期间递增。 对于Data Workbench中的查询，“报 <span class="wintitle"> 告时间” </span> 量度基于“截止”量度(“截止” <span class="filepath"> 量度)的午夜(As Of.metric </span>)。 由于“报告时间”量度的定义不同，如果查询使用“最后N”维的工作区，您可以在Data Workbench和 <span class="keyword"> Report Server中为同一工作区 </span> 接收不同的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 缩略图X </td> 
   <td colname="col2"> <i>可选</i>. 控制作为输出生成的缩览图X轴的大小（以像素为单位）的整数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 缩略图Y </td> 
   <td colname="col2"> <i>可选</i>. 控制作为输出生成的缩览图Y轴大小（以像素为单位）的整数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 前N个指标 </td> 
   <td colname="col2"> <p><i>可选</i>. 请参阅Top N值参数的说明。 </p> <p> <p>注意： 如果在此参数中输入值，则必须在“维名称”(Dimension Name)参数和“前N个值”(Top N Value)参数中输入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 前N个值 </td> 
   <td colname="col2"> <p><i>可选</i>. 填充此参数后， <span class="keyword"></span> Report Server以动态模式运行，并为“Dimension Name”（维名称）参数中指定的维的元素顶数（在此参数中指定）生成报表，按Top N Metric（前N个度量）参数中指定的度量计数。 </p> <p>示例：如果在“维名称”参数中输入“页”，在“前N个度量”参数中输入“会话”，在此参数中输入5，则生成的报告将列出具有最多会话数的前5个页面。 </p> <p> <p>注意： 如果在此参数中输入值，则必须在“维名称”参数和“前N个度量”参数中输入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 仅使用本地示例 </td> 
   <td colname="col2"> <i>可选</i>. 指示是否希望 <span class="keyword"> Report Server仅 </span> 使用数据集的本地示例生成报告。 将此参数设置为true使您能够查看报表集的示例（无需在Data Workbench Server上加载），以查看输出的外观，而无需花费完全处理数据所需的全部时间。 它用作测试函数。 选项为 true 或 false。默认值为false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作区路径 </td> 
   <td colname="col2"> <p><i>可选</i>. 给定报告集的工作区集合的位置。 这对于维护需要通过多种方式生成和分发的工作区的单个副本(使用 <span class="filepath"> Report.cfg文件 </span> 创建多个报表集)很有用。 此路径的根目录可以是任何配置文件文件夹。 请勿在路径字符串的开头输入斜杠(\)。 </p> <p>示例：您可以在 <span class="filepath"> Reports\Common文件夹中保存A组和B组的公用工作区，然后为两个不同的报告集定义 </span><span class="filepath"></span> Report.cfg文件，每个报告集具有不同的生成和分发设置。 在两个 <span class="filepath"> Report.cfg文件 </span> 中，您应将Workspace Path参数设置为配置文 <i>件名</i>\Reports\Common。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL输出文件 </td> 
   <td colname="col2"> <i>可选</i>. 将 <span class="wintitle"> XSL模板应用于报告索引时创 </span> 建的输出文件的路径。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL模板 </td> 
   <td colname="col2"> <p><i>可选</i>. 要应用于报告索引的XSL模板文件的路径。 生成的转 <span class="filepath"> 换的。xml </span> 将写入指定的 <span class="wintitle"> XSL输出文件 </span>。 有关 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> 示例文件，请参 </a> 阅报告示例文件。 </p> <p> <p>注意： 除非在生成报 <span class="filepath"> 表时使 </span> 用。xsl模板，否则所有报表都通过电子邮件作为附件分发。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

