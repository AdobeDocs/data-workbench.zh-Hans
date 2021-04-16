---
description: 有关Report.cfg参数的信息。
title: Report.cfg 参数
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2350'
ht-degree: 4%

---

# Report.cfg 参数{#report-cfg-parameters}

有关Report.cfg参数的信息。

[配置报表集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)中显示的示例[!DNL Report.cfg]默认仅包含[!DNL Report.cfg]文件中包含的参数。 下表提供所有可用[!DNL Report.cfg]文件参数的说明。

如果需要向[!DNL Report.cfg]文件添加其他参数，则必须使用文本编辑器进行添加。 要执行此操作的步骤（包括如何定义每个参数条目的示例），请参阅[编辑现有Report.cfg文件](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)。

>[!NOTE]
>
>此表中的参数按字母顺序列出。 当您以Data Workbench打开[!DNL Report.cfg]文件时，矢量按字母顺序列出，后跟按字母顺序列出的各个参数。

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
   <td colname="col2"> <p><i>可选</i>. 此参数仅适用于具有量度指示器的报表。 在发送警报报告之前必须出现在工作表中的量度指示器数。 </p> <p>如果在量度指示器工作表中只监视一个量度，请将阈值设置为1。 当工作表中的量度的计算结果为向上/向下箭头或X时，会生成报表。如果报表中正在监视多个量度，则可以选择在生成报表之前必须计算为向上/向下箭头或X的量度指示符数。 例如，如果监视两个量度： 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">如果阈值设置为1，则生成报表的条件是工作表中的任一量度评估为向上/向下箭头或X。 </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">如果阈值设置为2，则两个量度在生成报表之前必须计算为向上/向下箭头或X。 </li> 
     </ul> </p> <p>有关量度指示器的详细信息，请参阅<i>《Data Workbench用户指南》</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 允许报表再生 </td> 
   <td colname="col2"> <p>指示在创建或修改这些报表时，<span class="keyword">报表服务器</span>是否自动生成或重新生成特定报表。 选项为 true 或 false。如果设置为true，则创建或修改报表工作区会导致<span class="keyword">报表服务器</span>重新生成最近运行的报表。 </p> <p> <p>注意： 更改<span class="filepath"> Report.cfg </span>文件会导致<span class="keyword">报表服务器</span>重新生成由该<span class="filepath"> Report.cfg </span>文件控制的所有报表。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 附件 </td> 
   <td colname="col2"> <p><i>可选</i>. 通过电子邮件分发的报表传出的任何附件的名称和内容类型的章节标识符，包括附件数。 </p> <p>要添加新附件： 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">在Data Workbench中打开<span class="filepath"> Report.cfg </span>文件。 </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">右键单击<span class="uicontrol">附件</span>，然后单击<span class="uicontrol">添加新子项</span> &gt; <span class="uicontrol">附件</span>。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 内容类型 </td> 
   <td colname="col2"> <p>要附加的文件的内容类型。 </p> <p>示例：image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 文件名 </td> 
   <td colname="col2"> <p>要附加的文件的位置和名称。 </p> <p>示例：<span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color Set（颜色集） </td> 
   <td colname="col2"> 标识要用于<span class="filepath"> .png </span>文件的颜色方案。 0表示黑色背景；1表示白色背景；2用于灰度图像。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 要执行的命令 </td> 
   <td colname="col2"> <i>可选</i>. 在生成报表集后运行的批处理命令或可执行文件。 如果需要启动命令shell解释器，请在命令前面添加cmd /c。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 默认Excel模板 </td> 
   <td colname="col2"> <p><i>可选</i>. 将报表生成为Excel文件时要使用的通用Excel模板文件（<span class="filepath"> .xls </span>或<span class="filepath"> .xlsx </span>）的文件名。 此参数支持完整文件路径，如<span class="filepath"> c:\templates\mytemplate.xls </span>。 </p> <p>除非为特定报表专门定义了模板，否则此文件用于所有Excel报表。 请参阅<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751">使用模板文件</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维度名称 </td> 
   <td colname="col2"> <i>可选</i>. 要动态生成报表的维的名称。 如果在此参数中输入维名称，则必须在查找文件参数或前N个量度和前N个值参数中输入值。 此参数中命名的维度必须存在于创建报表的数据集中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 只有在完美时，才能发送电子邮件 </td> 
   <td colname="col2"> <i>可选</i>. 允许用户指定仅在运行期间未发生错误时才发送报表集。 选项为 true 和 false。默认值为 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 结束日期 </td> 
   <td colname="col2"> <p><i>可选</i>. 您希望报表集运行的上次日期和时间。 此时间基于数据集的“开始时间”。 </p> <p>格式：MM/DD/YYYY hh:mm时区，使用24小时时语法 </p> <p>示例：08/01/2007美国东部时间12:01 </p> <p>有关时区设置的详细信息，请参阅《数据集配置指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每个 </td> 
   <td colname="col2"> 生成报表集的频率：日、周或月。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excel监视程序超时（秒） </td> 
   <td colname="col2"> <p><i>可选</i>. 您希望<span class="keyword">报表服务器</span>在<span class="keyword">报表服务器</span>确定Excel未响应并终止该过程之前，等待Microsoft Excel作为Excel文件生成报表时响应的秒数。 使用此参数可使<span class="keyword">报表服务器</span>在Excel变得无响应时终止Excel并继续处理非Excel报表。 默认值为300.0。要禁用此功能，请将此参数设置为0.0。 </p> <p>确保您定义的值足够长，以允许将报表导出到Excel。 否则，<span class="keyword">报表服务器</span>可能会提前终止Excel，而您的报表将不会生成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 滤镜公式 </td> 
   <td colname="col2"> <p><i>可选</i>. 应用于报表集中每个工作区的过滤器。 </p> <p>有关详细信息，请参阅用于创建过滤器</a>的<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external">语法。 </a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 灰度系数校正 </td> 
   <td colname="col2"> <p><span class="filepath"> .png </span>文件输出的Gamma设置。 默认值为 1.6。 </p> <p> <p>注意： Adobe建议您不要更改此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隐藏徽标 </td> 
   <td colname="col2"> 指示在生成报表时报表服务器是否隐藏徽标。 选项为<span class="filepath"> true </span>或<span class="filepath"> false </span>。 如果设置为<span class="filepath"> false </span>，则会使用“报告”徽标生成您的报告。 默认值为<span class="filepath"> false </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查找文件 </td> 
   <td colname="col2"> <p><i>可选</i>. 填充此参数后，Report Server以动态模式运行，并为在“Dimension名称”参数中指定的维度的每个元素生成报表。 此文件必须包含两个制表符分隔的列，不含标题行。 </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">第1列包含维元素的列表。 </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">第2列包含报表收件人的电子邮件地址。 第1列中给定元素的报告将发送到第2列中同一行上的电子邮件地址。 您可以输入多个电子邮件地址，方法是用逗号（无空格）分隔它们。 如果不能通过电子邮件发送报表，则此列可为空，但必须存在。 </li> 
     </ul> </p> <p> <p>注意： 如果在此参数中输入值，则必须在“Dimension名称”参数中输入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 仅通知 </td> 
   <td colname="col2"> 此<span class="wintitle">报表服务器</span>设置允许您配置Data Workbench，以在生成报表时发送电子邮件。 将此值设置为<span class="filepath"> true </span>不会发出报告，而是发送一封电子邮件，通知订阅用户已生成报告。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 邮件报告 </td> 
   <td colname="col2"> <p>用于通过电子邮件分发报表的章节标识符。 要通过电子邮件分发报告，请填写<span class="wintitle">邮件报告</span>条目的以下参数。 报表集中的所有报表都通过电子邮件发送到收件人参数中指定的电子邮件地址。 </p> <p> <p>注意： 仅当报表服务器已生成至少一个报表时，才会发送电子邮件。 </p> </p> <p>要启用报表的电子邮件发送，您必须至少为此条目完成以下参数： 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP服务器 </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">收件人 </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">发件人地址 </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">仅通知 </li> 
     </ul> </p> <p> <p>注意： 要在重新生成报表集后通过电子邮件发送报表，请参阅<a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887">编辑现有Report.cfg文件</a>。 </p> </p> <p>“仅通知”值在5.4x和5.5x版本中可用。 </p> <p>对于要通知的大量收件人（超过20个），强烈建议您使用电子邮件分发列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 正文XSL模板 </td> 
   <td colname="col2"> <p><i>可选</i>. 要应用于<span class="filepath"> reports.xml </span>文件的XSL模板文件的路径。 使用此参数，报表服务器可以在分布式电子邮件中发送您的报表，而不是作为附件发送。 生成的文本将用作电子邮件正文。 </p> <p>有关示例文件，请参阅<a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87">报告示例文件</a>。 </p> <p>有关可扩展样式表语言(XSLT)的信息，请参阅<a href="http://www.w3.org/Style/XSL/" format="http" scope="external">可扩展样式表语言系列</a>。 </p> </td> 
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
   <td colname="col2"> 可选。发件人的姓名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP服务器 </td> 
   <td colname="col2"> SMTP服务器计算机的地址以及身份验证所需的密码和用户名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主题 </td> 
   <td colname="col2"> <i>可选</i>. 描述要发送的电子邮件的主题行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 仅通知 </td> 
   <td colname="col2"> 允许您配置Data Workbench，以便在生成后台报表时发送电子邮件。 将此值设置为True不会发出报表，而是发送将订阅用户链接到报表位置的电子邮件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 输出根 </td> 
   <td colname="col2"> <p><i>可选</i>. 生成的报表集的输出位置。 默认为Report Server安装目录中的<i>&lt;用户档案名&gt;</i>\Reports文件夹。 </p> <p>要将<span class="keyword">报表服务器</span>配置为将报表输出到门户，请将<span class="wintitle">输出根</span>设置为用于门户的Web服务器的文档根。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 预载查询滤镜 </td> 
   <td colname="col2"> <p><i>可选</i>. 此参数仅适用于<span class="wintitle">顶部Dimension元素</span>报告类型。 </p> <p>要应用于必须运行的查询的筛选器的名称，以确定在生成报表之前的前N个维度元素。 默认值为<span class="wintitle"> Broken_Session_Filter </span>。 有关<span class="wintitle">中断会话过滤器</span>的详细信息，请参阅<i>Data Workbench用户指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 报表类型 </span> </td> 
   <td colname="col2"> <p>要生成输出的格式。 可使用以下任意或全部选项一次以多种格式输出报表集： 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel会创建一个Excel工作簿，每个工作表有一个可视化。 通常，使用Excel文件进行电子邮件分发。 请参阅<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee">将报表生成为Microsoft Excel文件</a>。 有关使用模板文件的信息，请参阅<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751">使用模板文件</a>。 </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png创建可移植网络图形文件。 通常，使用<span class="filepath"> .png </span>文件在Web浏览器（门户）中显示。 </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">缩览图创建工作区的缩览图（<span class="filepath"> .jpg </span>文件）。 默认大小为240x180。 要更改默认大小，请编辑Thumbnail X和Thumbnail Y参数。 </li> 
     </ul> </p> <p>要在Data Workbench中编辑<span class="filepath"> Report.cfg </span>时添加新的报表类型，请右键单击<span class="uicontrol">报表类型</span>，单击<span class="uicontrol">添加新子项</span>，然后选择所需的报表类型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 开始日期 </td> 
   <td colname="col2"> <p>您希望报表集运行的第一个日期和时间。 此时间基于数据集的“开始时间”。 </p> <p>格式：MM/DD/YYY hh:mm时区，使用24小时语法表示时间。 </p> <p>有关时区设置的详细信息，请参阅《数据集配置指南》<i></i>。 </p> <p> <p>注意： 当用户档案中数据的时间戳与指定的日期和时间匹配时运行的报表开始。 </p> </p> <p>示例： </p> <p>如果开始日期为08/08/2006 12:00 EST，则报表会为时间戳为08/08/2006 12:00 EST及更高版本的数据运行。 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">每日报告将运行08/08/2006次，之后每天运行hh:mm = 12:00 EST的数据。 </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">每周报告将运行08/08/2006次，之后每7天对于EST为hh:mm = 12:00的数据运行一次。 </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">月度报告将运行08/08/2006次，之后每月第8天的EST为hh:mm = 12:00的数据。 </li> 
     </ul> </p> <p><span class="wintitle">报告时间</span>量度影响“Last N”报告维度，如“Last 7 Days”、“Yesterday”和“3 weeks ago.”。 对于报表服务器中的查询,<span class="wintitle">报表时间</span>量度（<span class="filepath">报表时间.metric </span>）标识报表运行的日期和时间。 这最初是在“开始日期”参数中指定的日期和时间，然后按“每个”参数指定的期间递增。 对于Data Workbench中的查询,<span class="wintitle">报表时间</span>量度基于“截止”量度（<span class="filepath">“截止。量度</span>）的午夜。 由于“报表时间”量度的定义不同，如果查询使用“最后一个N”维度的工作区，则可以在Data Workbench和<span class="keyword"> Report Server </span>中为同一工作区接收不同结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 缩略图X </td> 
   <td colname="col2"> <i>可选</i>. 控制作为输出生成的缩览图X轴大小（以像素为单位）的整数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 缩览图Y </td> 
   <td colname="col2"> <i>可选</i>. 控制作为输出生成的缩览图Y轴大小（以像素为单位）的整数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 前N个量度 </td> 
   <td colname="col2"> <p><i>可选</i>. 请参阅Top N值参数的说明。 </p> <p> <p>注意： 如果在此参数中输入值，则必须在“Dimension名称”参数和“前N值”参数中输入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 前N值 </td> 
   <td colname="col2"> <p><i>可选</i>. 填充此参数后，<span class="keyword">报表服务器</span>以动态模式运行，并生成“Dimension名称”参数中指定维度的元素顶数（在此参数中指定）的报表，按“前N个量度”参数中指定的量度计数。 </p> <p>示例：如果您在“Dimension名称”参数中输入“页面”，在“前N个量度”参数中输入“会话”，在此参数中输入5，则生成的报告将列表具有最多会话数的前5个页面。 </p> <p> <p>注意： 如果在此参数中输入值，则必须在“Dimension名称”参数和“前N个量度”参数中输入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 仅使用本地示例 </td> 
   <td colname="col2"> <i>可选</i>. 指示是否希望<span class="keyword">报表服务器</span>仅使用数据集的本地示例生成报表。 将此参数设置为true使您能够视图报表集的示例（无需在Data Workbench Server上加载），以查看输出的外观，而无需花费完全处理数据所需的所有时间。 它作为测试函数运行。 选项为 true 或 false。默认值为false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作区路径 </td> 
   <td colname="col2"> <p><i>可选</i>. 给定报表集的工作区集合的位置。 这对于使用<span class="filepath"> Report.cfg </span>文件保存需要生成并以多种方式分发的工作区的单个副本非常有用。 此路径的根目录可以是任何用户档案文件夹。 请勿在路径字符串的开始输入斜杠(\)。 </p> <p>示例：您可以在<span class="filepath"> Reports\Common </span>文件夹中保存Set A和Set B的常用工作区，然后为两个不同的报表集定义<span class="filepath"> Report.cfg </span>文件，每个报表集具有不同的生成和分发设置。 在两个<span class="filepath"> Report.cfg </span>文件中，您应将Workspace Path参数设置为<i>用户档案名称</i>\Reports\Common。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL输出文件 </td> 
   <td colname="col2"> <i>可选</i>. 将<span class="wintitle"> XSL模板</span>应用到报表索引时创建的输出文件的路径。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL模板 </td> 
   <td colname="col2"> <p><i>可选</i>. 要应用到报表索引的XSL模板文件的路径。 生成的转换后的<span class="filepath"> .xml </span>被写入指定的<span class="wintitle"> XSL输出文件</span>。 有关示例文件，请参阅<a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87">报告示例文件</a>。 </p> <p> <p>注意： 除非在生成报表时使用<span class="filepath"> .xsl </span>模板，否则所有报表都通过电子邮件作为附件分发。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
