---
description: 配置文件 Transform Mode.cfg 可让您暂停将数据处理到数据集中、指定离线源或指定运行转换功能的 Data Workbench Server 保存其状态文件的频率。
title: Transform Mode.cfg 文件
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 72%

---

# Transform Mode.cfg 文件{#the-transform-mode-cfg-file}

配置文件 Transform Mode.cfg 可让您暂停将数据处理到数据集中、指定离线源或指定运行转换功能的 Data Workbench Server 保存其状态文件的频率。

对 [!DNL Transform Mode.cfg] 文件进行更改（包括添加或删除源）不会导致重新处理数据。

**编辑数据集配置文件的 Transform Mode.cfg 文件**

1. 在要导出其数据的配置文件中工作时，打开[!DNL Profile Manager]并单击&#x200B;**[!UICONTROL Dataset]**&#x200B;以显示目录的内容。
1. 右键单击[!DNL Transform Mode.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。
1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现[!DNL Transform Mode.cfg]窗口。
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
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> 在新源的参数中，输入日志序列的掩码。对于文件名称格式为 <span class="filepath">YYYYMMDD-SENSORID.vsl</span> 的传感器日志源，掩码是 <i>SENSORID SENSORID</i>，并且区分大小写。对于日志文件日志源，掩码是由<span class="wintitle">掩码模式</span>提取的字符串（请参阅<a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e">日志文件</a>）。 </li> 
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

   在 Data Workbench 窗口内编辑 [!DNL Transform Mode.cfg] 文件时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。此外，您还可以使用快捷方式将文本从一个配置文件([!DNL .cfg])复制并粘贴到另一个配置文件。

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。
1. 若要使本地所做的更改生效，请在[!DNL Profile Manager]中右键单击[!DNL User]列中Data Workbench [!DNL Transform Mode.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]**，其中“配置文件名称”是要为其导出数据的配置文件名称。 在配置文件同步之后，系统便会开始重新处理数据。

   有关重新处理数据以进行导出的信息，请参阅[重新处理和重新转换](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
