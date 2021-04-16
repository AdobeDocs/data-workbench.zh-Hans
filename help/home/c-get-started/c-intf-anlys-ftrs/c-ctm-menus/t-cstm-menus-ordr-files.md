---
description: 您可以通过编辑与菜单相关联的 order.txt 文件来自定义任何菜单的外观。
title: 使用 order.txt 文件自定义菜单
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 69%

---

# 使用 order.txt 文件自定义菜单{#customize-a-menu-using-order-txt-files}

您可以通过编辑与菜单相关联的 order.txt 文件来自定义任何菜单的外观。

本节中的步骤适用于所有菜单类型。

**编辑 order.txt 文件以自定义菜单**

1. 在[!DNL Profile Manager]的&#x200B;*用户档案名称*&#x200B;列中，右键单击[!DNL order.txt]文件的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。
1. 右键单击[!DNL User]列中[!DNL order.txt]文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 将显示[!DNL order.txt]文件。

   ![步骤信息](assets/cfg_ordertxt.png)

1. （可选）如果需要，可在文件顶部添加或更改[Inclusive]或[Exclusive]设置。 此设置控制菜单上是否列出未列在[!DNL order.txt]文件中但存在于[!DNL Profile Manager]中的项目。 选项包括：

   * **[包含]:** 这是默认设置。该设置导致 [!DNL order.txt] 文件中未指定的菜单项按照字母顺序列在菜单的底部。例如，如果[!DNL Profile Manager]除了上面[!DNL order.txt]中列出的项之外，还包含用户档案项，则用户档案将显示在“数据”下方。

   * **[独占]:** 此设置导致菜单中未在文件中指定 [!DNL order.txt] 的菜单项从菜单中排除。例如，如果[!DNL Profile Manager]除了上面[!DNL order.txt]中列出的项之外还包含用户档案项，则菜单上的任何位置都不会显示用户档案。

   * **空白：** 如果 [] “包 [] 括”或“排除”都不显示在文件顶部，Data Workbench将像设置为“包含”一样显示菜 [单项]。

1. 完成以下一个或多个步骤：

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 若要执行此任务... </th> 
    <th colname="col2" class="entry"> 请执行以下操作... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>对菜单项重新排序 </p> </td> 
    <td colname="col2"> <p>按您希望项目名称以Data Workbench显示的顺序键入项目名称。 </p> <p>例如，只要每个菜单项名称与其对应的文件或文件夹名称相匹配，下面的内容便将导致首先显示<b>添加表格</b>，然后显示<b>添加可视化</b>、<b>添加图例</b>，最后显示<b>添加注释</b>。 </p> <p><b>添加表格 </b> </p> <p><b>添加可视化 </b> </p> <p><b>Add Legend </b> </p> <p><b>添加注释 </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>重命名菜单项 </p> </td> 
    <td colname="col2"> <p>在“<span class="wintitle">配置文件管理器</span>”中重命名对应的文件或文件夹，然后在 <span class="filepath">order.txt</span> 文件中更改项目的名称。 </p> <p>例如，若要将 Add Annotation（添加批注）重命名为 New Annotation（新建批注），请在“<span class="wintitle">配置文件管理器</span>”中将 Add Annotation 文件夹重命名为 New Annotation，然后在 <span class="filepath">order.txt</span> 文件中将 Add Annotation 项目的名称更改为 New Annotation。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>隐藏菜单项 </p> </td> 
    <td colname="col2"> <p>若要隐藏菜单项而不删除项目本身，请在项目名称前面输入一个减号 (-)。 </p> <p>例如，下面的内容将导致 <span class="wintitle">Add Annotation</span>（添加批注）不会出现在菜单中。 </p> <p>Add Legend </p> <p>-Add Annotation </p> <p>要再次显示隐藏的菜单项，只需删除减号(-)或使用<span class="filepath"> Insight.cfg</span>文件中的“全部取消隐藏”参数，请参阅<a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight配置参数</a>。 </p> <p>您也可以使用下面的方法来隐藏菜单项： 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p><span class="filepath">.filter</span>、<span class="filepath">.metric</span> 或 <span class="filepath">.dim</span> 文件中的 Show（显示）参数可隐藏对应菜单中的过滤器、派生量度和维度以及扩展维度。当您使用此选项时，项目将不会列在菜单中，但它仍然在配置文件中并且仍可使用。 </p> <p>若要使用此参数隐藏过滤器及派生量度和维度，请在 <span class="filepath">.metric</span>、<span class="filepath">.dim</span> 或 <span class="filepath">.filter</span> 文件的末尾添加下面一行： </p> <p><span class="filepath"> show = bool: false</span> </p> <p>若要使用此参数来隐藏扩展维度，请参阅《数据集配置指南》<i></i>的第 10 章以获取相关说明。 </p> <p>可以通过设置 <span class="filepath">Insight.cfg</span> 文件中的 Unhide All（全部取消隐藏）参数，暂时取消隐藏使用此方法隐藏的项目。有关此参数的详细信息，请参阅<a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight Configuration Parameters</a>。 </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA"><span class="filepath">Transformation.cfg</span> 文件或任何数据集包含文件中的 Hidden（隐藏）参数可隐藏维度菜单中的扩展维度。当您使用此选项时，项目将不会列在菜单中，但它仍然在配置文件中并且仍可使用。 <p> <p>注意：当使用此方法隐藏扩展维度时，必须针对要隐藏的维度重塑数据集。 </p> </p> <p>可以通过设置 <span class="filepath">Insight.cfg</span> 文件中的 Unhide All（全部取消隐藏）参数，暂时取消隐藏使用此方法隐藏的项目。有关此参数的详细信息，请参阅<a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight Configuration Parameters</a>。 </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>零字节文件可隐藏任何菜单中任何类型的项目。当使用此选项时，空（零字节）文件会隐藏包含数据的同名文件。Data Workbench将零字节文件视为它们不存在。 有关详细信息，请参阅<a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491">使用空（零字节）文件隐藏文件</a>。 </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>删除菜单项 </p> </td> 
    <td colname="col2"> <p>如果将该文件设置为使用 [Exclusive]（[独占]）选项，则只需从该文件中删除菜单项。项目本身仍然在配置文件中，但却不列在菜单中。 </p> <p>如果将该文件设置为使用 [Inclusive]（[包含]）选项，则必须从该文件中删除菜单项名称，并删除对应文件或对其进行零字节处理，这样才能从菜单中删除项目。 </p> <p>有关删除文件的信息，请参阅<a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b">从工作配置文件中删除文件</a>。有关零字节文件的信息，请参阅<a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491">使用空（零字节）文件隐藏文件</a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>添加组标题 </p> </td> 
    <td colname="col2"> <p>在您希望显示的标题文本前面和后面分别键入三个连字符。 </p> <p>例如，下面的内容将为一组相关菜单项添加一个 Manage（管理）组标题。 </p> <p>---管理--- </p> <p>用户档案 </p> <p>Dataset </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>添加一条直线以分隔菜单的各个部分 </p> </td> 
    <td colname="col2"> <p>在要显示直线的位置键入三个连字符。 </p> <p>例如，下面的内容将导致用一条直线分隔 Add Annotation（添加批注）和 Add Custom（添加自定义）。 </p> <p>Add Annotation </p> <p>— </p> <p>Add Custom </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 保存并关闭该文件。
1. （可选）要使更改对工作用户档案的所有用户可用，请右键单击[!DNL User]列中[!DNL order.txt]文件的白色复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**。
