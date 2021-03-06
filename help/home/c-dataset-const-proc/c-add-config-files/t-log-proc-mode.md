---
description: 配置文件 Log Processing Mode.cfg 可让您暂停将数据处理到数据集中、指定离线源或指定 Data Workbench Server 保存其状态文件的频率。
title: Log Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 76%

---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

配置文件 Log Processing Mode.cfg 可让您暂停将数据处理到数据集中、指定离线源或指定 Data Workbench Server 保存其状态文件的频率。

对 [!DNL Log Processing Mode.cfg] 文件进行更改（包括添加或删除源）不会导致重新处理数据。

**编辑数据集配置文件的 Log Processing Mode.cfg 文件**

1. 在处理数据集配置文件时，打开[!DNL Profile Manager]并单击&#x200B;**[!UICONTROL Dataset]**&#x200B;以显示其内容。

   >[!NOTE]
   >
   >如果[!DNL Log Processing Mode.cfg]文件不在所需配置文件的目录中，则需要将此文件从Data Workbench Server计算机上的Base目录复制到配置文件的目录中。

   有关打开和使用[!DNL Profile Manager,]的信息，请参阅&#x200B;*Data Workbench用户指南*。

1. 右键单击配置文件名称旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。
1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此时会出现配置窗口。
1. 参考下表，编辑该配置文件中的参数。

   >[!NOTE]
   >
   >[!DNL Log Processing Mode.cfg]文件中的某些参数的名称包括[!DNL Fast Input]或[!DNL Fast Merge]。 [!DNL Fast Input]是指数据集构建的日志处理阶段，大约占数据集处理总时间的一半。[!DNL Fast Merge] 是指仅在进行日志处理之前的数据集构建的转换阶段。[!DNL Fast Merge] 在修改文件后导致的重新转换期间不 [!DNL Transformation Dataset Configuration] 发生。与[!DNL Fast Input]类似， [!DNL Fast Merge]也负责大约一半的数据集处理时间。

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 参数 </th> 
      <th colname="col2" class="entry"> 描述 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Cloud Bytes（云字节数） </td> 
      <td colname="col2"> <p>影响数据转换效率的调整参数。默认值为 128000000。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，不应更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input Decision Ratio（快速输入决策比率） </td> 
      <td colname="col2"> <p>指定总日志字节数与未读取日志字节数比率的调整参数，在达到此比率时，系统将进入“<span class="wintitle">快速输入</span>”模式（随后进入“<span class="wintitle">快速合并</span>”）而不是实时处理数据。 </p> <p> 默认值为 200，表示当未读取日志数据为总数据的 1/200 时，系统将从实时模式进入“<span class="wintitle">快速输入</span>”模式。较高的决策比率会使系统较容易地进入“<span class="wintitle">快速输入</span>”模式，而较低的比率则使系统不太可能进入“<span class="wintitle">快速输入</span>”模式。 </p> <p> <p>注意：将该参数设为 0 会导致系统根本无法进入“<span class="wintitle">快速输入</span>”模式，即使对于初始处理也是如此。将参数设为 1.1，可允许系统在初始处理过程中进入“<span class="wintitle">快速输入</span>”，但在后续处理期间则不行。Adobe 不建议使用 0 到 1.1 之间的值。有关设置此参数的详细信息，请联系 Adobe。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input FIFO Bytes（快速输入 FIFO 字节数） </td> 
      <td colname="col2"> <p>在数据处理过程中平衡内存使用与系统性能的调整参数。默认值为 120000000。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，不应更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Merge Buffer Bytes（快速合并缓冲字节数） </td> 
      <td colname="col2"> <p>在数据处理过程中平衡内存使用与系统性能的调整参数。默认值为 128000000。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，不应更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offline Sources（离线源） </td> 
      <td colname="col2"> <p>离线日志源的掩码。 </p> <p> <b> 指定离线源</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> 右键单击<span class="uicontrol">离线源</span>，然后单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">源</span>。 </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> 在新源的参数中，输入日志序列的掩码。对于文件名称格式为 YYYYMMDD-<i>SENSORID</i>.vsl 的“传感器”日志源，掩码为 <i>SENSORID.SENSORID</i>，并且此掩码区分大小写。对于日志文件日志源，掩码是由<span class="wintitle">掩码模式</span>提取的字符串。 请参阅<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e">日志文件</a>。 </li> 
      </ul> </p> <p> 向“离线源”中添加源或从中删除源不会导致重新处理数据集。 </p> <p> 为了处理配置文件的在线源，会持续进行“截至”时间测量。当离线源重新在线时，对该源的传入日志文件的处理便会恢复。 </p> <p> 只要源恢复到在线状态，您就应该从“离线源”中将其删除。如果您没有这样做，Data Workbench Server 会将该源视为在线源，并且只要该源发送数据，该服务器便会更新“截至”时间。如果该源重新变为离线状态，则“截至”时间测量将停止。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Paused（暂停） </td> 
      <td colname="col2"> true 或 false。如果为 true，则新数据不会处理到数据集中。默认值为 false。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Real Time Delay（实时延迟） </td> 
      <td colname="col2"> 在将数据处理到数据集的间隔期间，Data Workbench Server 所等待的时间（以秒为单位）。当此值设为零时，系统会尝试实时获取传入数据。默认值为零 (0)，但您可以增大此值以减少 CPU 负载。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Real Time FIFO Bytes（实时 FIFO 字节数） </td> 
      <td colname="col2"> <p>用于存储正等待处理到数据集中的数据的内存量，以字节为单位。您可能需要根据为 Real Time Delay（实时延迟）指定的秒数更改此值。默认值为 16000000。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，不应更改此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Save Interval (sec)（保存时间间隔（秒）） </td> 
      <td colname="col2"> <p>Data Workbench Server 保存其状态文件的频率。默认值为 3600。 </p> <p> <p>注意：在未咨询 Adobe 的情况下，不应更改此值。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   在 Data Workbench 窗口内编辑 [!DNL Log Processing Mode.cfg] 文件时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。此外，您还可以使用快捷方式将文本从一个配置文件([!DNL .cfg])复制并粘贴到另一个配置文件。

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。
