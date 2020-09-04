---
description: Data Workbench 6.2 发行说明包括新增功能、升级要求、错误修复和已知问题。
title: Data Workbench 6.2 发行说明
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 83%

---


# Data Workbench 6.2 发行说明{#data-workbench-release-notes}

Data Workbench 6.2 发行说明包括新增功能、升级要求、错误修复和已知问题。

## 新增功能 {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.2 包含以下新增功能：

| 功能 | 描述 |
|--- |--- |
| 决策树 | 决策树是对预测分析的可视化，用于评估访客特性与关系。决策树生成器根据指定的正类用例和一组输入生成决策树可视化。 |
| 更新关联矩阵中的二进制过滤器 | 已使用新功能更新二进制过滤器，需要重新生成具有在以前版本中生成的二进制过滤器的任何关联矩阵。 |
| 密度图 | 密度图是在方形图中将元素显示为阴影矩形的可视化。 |
| 归因配置文件 | 为了快速分析归因值（将成功转化或销售的责任归因于的事件），Data Workbench 提供了一个基于规则的归因配置文件和相应的功能，以使架构师能够设置归因报表并使分析师能够运行这些报表。 |
| 分析报表 | 报表模板为使用 Adobe SC 配置文件的 Data Workbench 用户标准化 Adobe Analytics 的报表。这些报表与 Marketing Reports &amp; Analytics（以前称为 SiteCatalyst）中使用的报表完全相同。 |
| 3D 散点图 | 3D 散点图用三维网格绘制数据维度的元素（例如，“天数”或“推荐网站”），其中 x、y 和 z 轴表示各个量度。 |


## Data Workbench 客户端 UI 更新{#data-workbench-client-ui-updates}

Data Workbench 6.2 包含新的用户界面“书签”面板更新，在工作区工具栏中包含新的图标，具有在屏幕中拖动工作区的功能、新的快捷键以及饼图可视化更新。

## 新的书签功能 {#section-e361b605441540ca8213c3fddb5e0718}

现在，您可以为重要工作区创建书签，以便在可视化工作流程中使用的报表之间快速移动。

**使用书签**

1. 可通过单击工具栏右上角的书签图标 ![](assets/bookmark_icon.png)，为工作区创建书签。
1. 单击左侧窗格中的“**[!UICONTROL 添加]**”>**[!UICONTROL “书签”面板]**&#x200B;以打开书签列表。

   ![](assets/bookmarks_panel.png)

1. 要打开添加了书签的工作区，请在&#x200B;**[!UICONTROL 书签面板]**&#x200B;中单击工作区名称。

   ![](assets/bookmarks_panel_left.png)

   所选工作区将会打开。当您单击另一个添加了书签的工作区时，之前的工作区会关闭，新选的工作区将打开，从而让您可以快速导航工作流。

**要删除书签：**

* In the Bookmark Panel, right-click and select **Remove`<bookmark title>`** to delete a selected bookmark, or select **[!UICONTROL Clear All Bookmarks]** to delete all bookmarks.

* 您也可以右键单击 Worktop 上缩略图中的工作区，并选择&#x200B;**[!UICONTROL 清除书签]**。

>[!IMPORTANT]
>
>* 可以保存 25 个书签。
>* 如果添加了书签，然后移动工作区的位置，书签将失效，必须从“书签”面板中将其删除并重置。

>



## 工作区中的新图标 {#section-c108bbd1661249e79c146727ff3d2470}

Data Workbench 6.2 现在将工作区中的文本替换为图标。您仍然可以悬停鼠标并查看标识图标的工具提示消息，包括“**[!UICONTROL 文件]**”、“**[!UICONTROL 添加]**”和“**[!UICONTROL 导出]**”。

![](assets/new_icons.png)

添加了新的&#x200B;**[!UICONTROL 帮助]**&#x200B;图标以访问文档和其他知识中心，包括以下链接：

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文档链接 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Marketing Reports &amp; Analytics </td> 
   <td colname="col2">打开 <span class="uicontrol">Adobe Marketing Reports &amp; Analytics</span> 帮助页面。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Idea Exchange </td> 
   <td colname="col2">打开“<span class="uicontrol">创意分享登录</span>”。通过使用此在线门户，用户可以在 Data Workbench 中提供更新更改和增强创意。然后，所有用户可以对这些以客户为中心的创意进行投票。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 帮助 </td> 
   <td colname="col2">打开 <span class="uicontrol">Data Workbench 文档</span>。 <p>也可以按 <span class="uicontrol">&lt;F1&gt;</span> 以在工作区中打开帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 关于 </td> 
   <td colname="col2">打开以指定 Data Workbench <span class="uicontrol">客户端版本</span>。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>You can also press `<F1>` to open the documentation from a workspace.

## 拖动工作区视图 {#section-9129c340c21d45a3864c923884cd4382}

如果工作区比可查看屏幕大，您可以移动视图以查看工作区中的所有元素。您可以在背景中单击（在可视化和表格外面），并拖动屏幕以在工作区中移动可查看区域。在工作区框架中拖动视图时，光标将变为手形图标。

![](assets/drag_workspace.png)

## 用于更改工作区视图的快捷键 {#section-d8322f72423f437aa2e34f2188b1341c}

通过使用新的快捷键，您可以调整大小，并在窗口和全页面视图之间重新调整工作区。

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 命令 </th> 
   <th colname="col2" class="entry"> 快捷键 </th> 
   <th colname="col3" class="entry"> 组合菜单命令 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>全屏视图</b>。工作区会充满屏幕，并重新调整为新大小。 </td> 
   <td colname="col2"><b>Ctrl +</b> <p>Ctrl +（在键盘上） </p> <p><i>或</i> </p> <p>Ctrl Shift +（在键盘上） </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">文件 &gt; 页面大小 &gt; 充满屏幕 <p><i>后跟</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">文件 &gt; 重新调整工作区 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>窗口视图</b>。工作区显示在标准窗口视图中，并重新调整为新大小。 </td> 
   <td colname="col2"><b>Ctrl -</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">文件 &gt; 页面大小 &gt; 标准 <p><i>后跟</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">文件 &gt; 重新调整工作区 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 错误修复 {#section-8704a9ac358246cd81233dd0982d534f}

* 已更新 Visual Site 查找文件，以处理搜索引擎更改了查询搜索词的问题。
* 修复了在客户端工作站中导入工作区时出现的不准确错误消息“无法导入工作区”（即使导入成功）。
* 显示“412 配置冲突”消息的工作站连接错误现在替换为指定系统操作的用户友好的消息。
* 现在，可以在 Report Server 中执行“post”命令。
* 修复了简体中文客户端用户界面中的用户界面错误。
* Adobe Analytics更新了支持Data Workbench利用与Adobe Experience Cloud集成的用户档案和受众的数据源。 所有 Data Workbench 用户需要在 2014 年 4 月 21 日之前准备好环境以完成此过渡。

   用户档案和受众被引入Adobe Analytics，为整个的客户提供全面视图。 此新服务在Adobe Experience Cloud提供，可跨分析工具进一步提升价值，开始在Analytics中为这些功能奠定基础。 新Experience Cloud访客标识符将被添加到数据源，以及其他增强和改进，以适应新数据源和全局访客标识符。
* 导入工作区时，即使导入成功也会显示错误消息。

## 更新要求 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* 为实施 Adobe SC 配置文件以使用 Analytics (SC/Insight) 数据源的用户配置了归因配置文件。默认情况下，将营销和转化事件作为在基于规则的模型中评估的默认交互。
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. 只有在将配置文件修改为非默认配置时，才会出现问题。

* If you have deleted unused fields in the **[!UICONTROL Dataset]** > **[!UICONTROL Log Processing]** > **[!DNL SC Fields.cfg]** file for the Adobe SC profile, you will need to update to accommodate updated field values used for the Attribution profile.

## 已知问题 {#section-dbb307639835493a83409f5f461932b8}

* 如果 3D 散点图可视化包含标注，缩放可能会在可视化边框以外显示图形。

   解决方案：先缩放 3D 散点图，然后在可视化中添加标注。
* 如果将量度从“查找器”面板拖到量度列外部的量度图例上，则会从工作区中删除量度图例。

   解决方案：要将量度拖到量度图例上的用户应将其放在第一列（量度列）中。
* 在使用“边栏”和“两者兼有”选项打印工作区时，打印的页面上不包含版权信息。
* 重命名工作区时，如果在远程桌面会话中使用工作站，则会导致系统崩溃。
* （在简体中文版本中）实际报表输出在 Report Server 中有效，但电子邮件主题行和附件文件名显示为乱码。
* （在简体中文版本中）在“工作表”可视化中使用自动换行时，本地化的字词没有正确换行，从而导致在字符串中添加乱码。
* （在简体中文版本中）如果安装目录名称中包含非英语字符，则无法启动 Insight.exe。

   解决方案：保留默认名称，或在文件夹路径中仅使用英语字符进行重命名以启动可执行文件。

