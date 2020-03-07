---
description: 您必须配置目标Insight Server，以从存储原始事件数据的Repeater检索数据。
solution: Insight
title: 配置复制服务
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置复制服务{#configuring-the-replication-service}

您必须配置目标Insight Server，以从存储原始事件数据的Repeater检索数据。

要配置从目标到目标的数 [!DNL Repeater] 据检索 [!DNL Insight Server]，您必须编辑目标文件夹中提 [!DNL Replicate.cfg] 供的文件，如以 [!DNL Components][!DNL Insight Server(s)] 下过程所述：

**在目标计[!DNL Replication Service]算机上配置**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。
1. 右键单击要配置的目标 [!DNL Insight Server] 的图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Replicate.cfg] 文件位于此目录中。
1. Right-click the check mark in the *server name* column for [!DNL Replicate.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Replicate.cfg].
1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 窗口 [!DNL Replicate.cfg] 将打开。
1. 在窗 [!DNL Replicate.cfg] 口中，单 **[!UICONTROL Replicate.cfg]**&#x200B;击，然 **[!UICONTROL component]** 后查看其内容。
1. 使用以下示例和表作为参考线编辑参数：

   ![步骤信息](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 对于该参数... </th> 
      <th colname="col2" class="entry"> 在“管理工具”中指定分类的... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 目录 </td> 
      <td colname="col2"> <p>要复制(复 <span class="wintitle"> 制</span> )到目标Insight Server的Repeater上的目 <span class="keyword"> 录</span>。 复制 <span class="wintitle"> 服务允许从一个Repeater复制多个目</span> 录 <span class="wintitle"></span>。 </p> <p>要添加新目录，请右键单击“目录 <span class="uicontrol"> ”</span> ，然后单击 <span class="uicontrol"> “添加新</span> &gt;目 <span class="uicontrol"> 录”</span>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拼合路径 </td> 
      <td colname="col2"> <p>true 或 false。由此参数的设置定义的操作取决于此文件中“递归”参数的设置： 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">如果“递归”为false，则“拼合路径”不起作用。 只复制由Remote URI参数指定的目录顶级的文件。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">如果“递归”为true,“拼合路径”为false，则远程(<span class="wintitle"> Repeater</span>)目录的目录结构将完全复制到目标Insight Server上的本地路径中 <span class="keyword"></span>。 </li>
      <li id="li_3114B191C73744658799E112C61AB004">如果“递归路径”和“拼合路径”都为true，则不会在本地路径中创建子目录。 而是将远程目录树中的所有文件放置在本地目录的顶级。 </li>
      </ul></p> <p> <p>注意：如果“拼合路径”和“递归”都为true，并且远程计算机上的不同子目录中的文件共享相同的名称，则 <span class="wintitle"> Replication Service</span> （复制服务）可能会停止，或者可能发生其他未定义的行为。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 本地路径 </td> 
      <td colname="col2">从Repeater检索到的文件的存储 <span class="wintitle"> 位置</span>。 The path is relative to the <span class="keyword"> Insight Server</span> installation directory. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursive（递归） </td> 
      <td colname="col2"> true 或 false。如果为false，则仅复制由Remote URI参数指定的目录顶级的文件。 请参阅此表中的拼合路径。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 远程URI </td> 
      <td colname="col2">用于访问Repeater的文件存储的URI(包括文 <span class="wintitle"> 件掩码</span> )。 应配 <span class="filepath"> 置Repeater上的</span><span class="wintitle"></span> Communications.cfg文件，以便使用此URI访问事件数据。 请参阅 <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> 监视事件数据空间</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 服务器 </td> 
      <td colname="col2">目标Insight Server从 <span class="wintitle"> 中检索事件数据文件的</span> Repeater <span class="keyword"></span> 的参数。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名称 </td> 
      <td colname="col2">可选。用于标识中继器的 <span class="wintitle"> 名称</span>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Server Common Name（SSL 服务器通用名称） </td> 
      <td colname="col2">仅当“使用SSL”设置为true时才需要。 存储事件数 <span class="wintitle"> 据的</span> Repeater的通用名称。 此名称必须与计算机的通信证书中列出的通用名称匹配。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 地址 </td> 
      <td colname="col2">存储事件数据的 <span class="wintitle"> Repeater</span> 的主机名或数字IP地址。 服务器的通用名称不是有效条目。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port（端口） </td> 
      <td colname="col2"> 用于数据传输的端口。 默认端口为 80。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
      <td colname="col2">仅当“使用SSL”设置为true时才需要。 用于连接到Repeater的许可证证书的名 <span class="wintitle"> 称</span>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Use SSL（使用 SSL） </td> 
      <td colname="col2"> <p>确定是否将SSL用于数据传输。 选项为true或false，默认值为false。 </p> <p> <p>注意：不建议使用SSL，因为它可能会对性能产生负面影响。 请注意，除非将Repeater连接到目标计算机的网络不 <span class="wintitle"> 安全</span> ，否则不需要SSL。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 结束时间，开始时间 </td> 
      <td colname="col2"> <p>（可选）将复制到目标 <span class="keyword"></span> Insight Server的事件数据文件集限制为包含“开始时间”和“结束时间”定义范围内的数据的文件集。 如果设置了“开始时间”，则不会复制所有日志条目来自指定开始时间之前的事件数据文件。 如果设置了“结束时间”，则不会复制其中指定时间或以后的所有日志条目的事件数据文件。 如果文件中的部分数据在指定范围内，则整个文件将复制到目标计算机。 </p> <p>Adobe 建议使用以下时间格式之一： 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">January 1 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">Jan 1 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：必须指定时区。 如果未指定，则时区不默认为系统时间。 If you wish to implement Daylight Saving Time or a similar clock-shifting policy, you must save the <span class="filepath"> .dst</span> file containing the appropriate rules in the Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> machine. 有关支持的时区缩写列表和有关实施夏令时的信息，请参阅 <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> 时区代码</a>。 </p> </p> <p> <p>注意： 要使用这些设置，事件数据文件的名称必须以ISO日期(YYYYMMDD)开头，并且每个文件必须包含该日期的24小时期间内的数据，该时间从格林尼治时间的凌晨12点开始。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记，然 [!DNL Temp] 后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

此示例说明如果“拼合路径”和“递归”参数均设置为true，则如何复制文件。

假定远程URI [!DNL /RemoteRoot/] 为，本地路径为[!DNL E:\LocalRoot\]。 在远程( [!DNL Repeater])计算机上，文件按如下方式组织：

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

复制完成后，本地目录具有以下文件：

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

在本地目录中，不会创建子目录，并且远程目录树中的所有文件都放置在本地目录的顶级。

>[!NOTE]
>
>如果远程计算机上的不同子目录中的文件共享相同的名称，则可能会停 [!DNL Replication Service] 止或发生其他未定义的行为。
