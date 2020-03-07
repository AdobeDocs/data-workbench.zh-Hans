---
description: 配置文件 Transform Mode.cfg 可让您暂停将数据处理到数据集中、指定离线源或指定运行转换功能的 Data Workbench Server 保存其状态文件的频率。
solution: Analytics
title: ' Transform Mode.cfg 文件'
topic: Data workbench
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


#  Transform Mode.cfg 文件{#the-transform-mode-cfg-file}

配置文件 Transform Mode.cfg 可让您暂停将数据处理到数据集中、指定离线源或指定运行转换功能的 Data Workbench Server 保存其状态文件的频率。

对 [!DNL Transform Mode.cfg] 文件进行更改（包括添加或删除源）不会导致重新处理数据。

**编辑数据集配置文件的 Transform Mode.cfg 文件**

1. While working in the profile whose data you want to export, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show the contents of the directory.
1. 右键单击旁边的复选标记， [!DNL Transform Mode.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 The [!DNL Transform Mode.cfg] window appears.
1. 参考下表，编辑该配置文件中的参数：

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 参数 </th> 
    <th colname="col2" class="entry"> 描述 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Offline Sources（离线源） </td> 
    <td colname="col2"> <p>离线日志源的掩码。 </p> <p> 指定离线源： </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> 右键单击<span class="uicontrol">离线源</span>，然后单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">源</span>。 </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> 在新源的参数中，输入日志序列的掩码。对于文件名称格式为 <span class="filepath">YYYYMMDD-SENSORID.vsl</span> 的传感器日志源，掩码是 <i>SENSORID SENSORID</i>，并且区分大小写。For log file log sources, the mask is the string extracted by the <span class="wintitle"> Mask Pattern</span> (see <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>). </li> 
    </ul> <p> 向“<span class="wintitle">离线源</span>”中添加源或从中删除源不会导致重新处理数据集。 </p> <p> 为了处理配置文件的在线源，会持续进行“截至”时间测量。当离线源重新在线时，对该源的传入日志文件的处理便会恢复。 </p> <p> <p>注意：只要源恢复到在线状态，您就应该从“<span class="wintitle">离线源</span>”中将其删除。如果您没有这样做，Data Workbench Server 会将该源视为在线源，并且只要该源发送数据，该服务器便会更新“截至”时间。如果该源重新变为离线状态，则“截至”时间测量将停止。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Paused（暂停） </td> 
    <td colname="col2"> true 或 false。如果为 true，则新数据不会处理到数据集中。默认值为 false。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Save Interval (sec)（保存时间间隔（秒）） </td> 
    <td colname="col2"> <p>运行转换功能的 Data Workbench Server 保存其状态文件的频率。默认值为 3600。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，不应更改此值。 </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   在 Data Workbench 窗口内编辑 [!DNL Transform Mode.cfg] 文件时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the data workbench [!DNL Transform Mode.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, where profile name is the name of the profile for which you are exporting data. 在配置文件同步之后，系统便会开始重新处理数据。

   有关重新处理数据以便导出的信息，请参阅重新 [处理和重新转换](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
