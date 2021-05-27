---
description: 可以使用 Data Workbench 中的“查找器”面板选择量度、维度和过滤器。这些面板提供了搜索支持、排序选项和拖放功能。
title: 查找器
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 96%

---


# 查找器{#finders}

可以使用 Data Workbench 中的“查找器”面板选择量度、维度和过滤器。这些面板提供了搜索支持、排序选项和拖放功能。

可以在左侧边栏或工作区中打开“查找器”面板。

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 维度查找器 </th> 
   <th colname="col2" class="entry"> 量度查找器 </th> 
   <th colname="col3" class="entry"> 过滤器查找器 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>查询模型中的所有维度的列表。 </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>查询模型中的所有量度的列表。 </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>为您的组织创建的所有过滤器的列表。 </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**要打开查找器，请执行以下操作：**

* 在工作区中右键单击并选择&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Finder]**。

   将在工作区中打开“查找器”窗格以及“量度”、“维度”和“过滤器”选项卡。

* 在左侧边栏中单击鼠标右键，然后选择&#x200B;**[!UICONTROL Add]** > **[!UICONTROL Finder]**。

   将在左侧面板中打开“查找器”窗格。

**查找器**&#x200B;包含以下功能：

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 查找器功能 </th> 
   <th colname="col2" class="entry"> 详细信息 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>拖放</b> </td> 
   <td colname="col2"> <p> 可以将维度或量度从面板拖放到工作区中的可视化以更改维度或添加新量度。 </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">按住 <span class="uicontrol">&lt;Ctrl&gt;</span> 和 <span class="uicontrol">&lt;Alt&gt;</span> 键，然后从“查找器”面板中选择维度或量度。 </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">将新的维度从窗格拖放到可视化以更改或添加维度。 </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">要添加量度，请将新量度从窗格拖放到选定可视化的量度标题上。 </li> 
    </ol> <p>这适用于所有相关的可视化，包括表格、访客聚类、关联矩阵、散点图和 2D 条形图（取决于轴）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>搜索</b> </td> 
   <td colname="col2">通过使用“查找器”面板中的“<span class="uicontrol">搜索</span>”框，您可以过滤维度、量度和过滤器的名称。 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>模式匹配（简单 glob 搜索）。在“搜索”字段中开始键入所需的维度、量度或过滤器实体的名称，仅在“查找器”窗格中过滤和显示在名称中的任意位置包含的匹配字符串。 </p> <p>例如，输入： </p> <code><b>Search:</b>click</code> <p>可能会在维度查找器中获得以下结果： </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>标准模式匹配允许使用通配符，例如，.（点）、“?”和“*”（星号）。 </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>正则表达式. 还支持更复杂的正则表达式以增加搜索功能。可以在搜索词前面添加前缀“re:”（不含空格）以解释为正则表达式。 </p> <p>例如，输入： </p> <code><b>Search:</b>re.*ip</code> <p>可能会在维度查找器中获得以下结果： </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>有关详细的搜索信息，请参阅<a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external">正则表达式</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>维度类型</b> </td> 
   <td colname="col2">在“维度”选项卡中，您可以右键单击选项卡标题以按维度类型进行排序。 <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">属性 - 根据访客、产品、地域、时间、视频和其他属性的特性生成的维度。 </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">聚类 - 在聚类生成器中生成的维度。 </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">分数 - 在倾向评分中生成的维度。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>标签</b> </td> 
   <td colname="col2">在每个选项卡中，您可以右键单击并选择“<span class="uicontrol">标签</span>”以重命名“查找器”窗格。 <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>可以将默认“维度”、“量度”和“过滤器”标签更改为满足您的组织惯例的标签名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>添加项目</b> </td> 
   <td colname="col2">在每个选项卡中，您可以右键单击并选择“<span class="uicontrol">添加项目</span>”以打开一个表格，然后手动添加维度、量度和过滤器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>“查找器”栏</b> </td> 
   <td colname="col2">在左侧边栏的“<span class="uicontrol">查找器</span>”栏中单击鼠标右键以打开一个包含附加功能的菜单。 <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>关闭</b> </td> 
   <td colname="col2">在“<span class="uicontrol">查找器</span>”栏中右键单击并选择“<span class="uicontrol">关闭</span>”以关闭“查找器”窗格。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>保存</b> </td> 
   <td colname="col2">右键单击标题栏并选择“<span class="uicontrol">保存</span>”选项以在本地保存列表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>导出</b> </td> 
   <td colname="col2">可通过在“查找器”栏中右键单击并从菜单中选择“<span class="uicontrol">导出</span>”，从“查找器”面板中导出一组选定的维度、量度或过滤器。 <p> 添加名称并导出到 Microsoft Excel。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copy</b> </td> 
   <td colname="col2"> 复制一组维度、量度或过滤器。您可以在深色背景、浅色背景或单色中以文件或图形形式进行复制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>最小化</b> </td> 
   <td colname="col2"> 最小化“查找器”窗格。将仅显示“查找器”栏。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>无边框</b> </td> 
   <td colname="col2"> 显示一个窗格，并且在工作区中没有查找器的边框线（而不是在左侧边栏中）。 </td> 
  </tr> 
 </tbody> 
</table>

