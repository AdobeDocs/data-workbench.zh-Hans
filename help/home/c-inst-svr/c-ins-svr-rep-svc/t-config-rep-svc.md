---
description: 您必须配置目标Insight Server，以从存储原始事件数据的中继器中检索数据。
title: 配置复制服务
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 6%

---

# 配置复制服务{#configuring-the-replication-service}

您必须配置目标Insight Server，以从存储原始事件数据的中继器中检索数据。

要配置从[!DNL Repeater]到目标[!DNL Insight Server]的数据检索，必须按照以下过程所述编辑目标[!DNL Insight Server(s)]上[!DNL Components]文件夹中提供的[!DNL Replicate.cfg]文件：

**在目标计 [!DNL Replication Service] 算机上配置**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。
1. 右键单击要配置的目标[!DNL Insight Server]的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;以查看其内容。 [!DNL Replicate.cfg] 文件位于此目录中。
1. 右键单击&#x200B;*服务器名称*&#x200B;列中[!DNL Replicate.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中会出现[!DNL Replicate.cfg]的复选标记。
1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 将打开[!DNL Replicate.cfg]窗口。
1. 在[!DNL Replicate.cfg]窗口中，单击&#x200B;**[!UICONTROL Replicate.cfg]**，然后单击&#x200B;**[!UICONTROL component]**&#x200B;以查看其内容。
1. 参考以下示例和表格，编辑参数：

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
      <td colname="col2"> <p>要复制（复制）到目标<span class="keyword"> Insight Server</span>的<span class="wintitle">中继器</span>上的目录。 <span class="wintitle">复制服务</span>允许从单个<span class="wintitle">中继器</span>复制多个目录。 </p> <p>要添加新目录，请右键单击<span class="uicontrol">目录</span> ，然后单击<span class="uicontrol">添加新</span> &gt; <span class="uicontrol">目录</span>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 扁平化路径 </td> 
      <td colname="col2"> <p>true 或 false。此参数设置定义的操作取决于此文件中Recursive（递归）参数的设置： 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">如果Recursive为false，则Flatten Paths不起作用。 只复制Remote URI参数指定目录顶级的文件。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">如果Recursive（递归）为true , Flatten Paths（扁平化路径）为false，则远程(<span class="wintitle"> Repeater</span>)目录的目录结构将完全复制在目标<span class="keyword"> Insight Server</span>上的本地路径中。 </li>
      <li id="li_3114B191C73744658799E112C61AB004">如果“递归路径”和“扁平化路径”均为true，则不会在本地路径中创建子目录。 而远程目录树中的所有文件都放置在本地目录的顶级中。 </li>
      </ul></p> <p> <p>注意：如果“扁平化路径”和“递归”都为true，并且远程计算机上各个子目录中的文件共享相同的名称，则<span class="wintitle">复制服务</span>可能会停止或发生其他未定义的行为。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 本地路径 </td> 
      <td colname="col2">从<span class="wintitle">中继器</span>中检索到的文件的存储位置。 路径相对于<span class="keyword"> Insight Server</span>安装目录。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursive（递归） </td> 
      <td colname="col2"> true 或 false。如果为false，则只复制Remote URI参数指定目录顶级的文件。 请参阅此表中的扁平化路径。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 远程URI </td> 
      <td colname="col2">用于访问<span class="wintitle">中继器</span>文件存储的URI，包括文件掩码。 应配置<span class="wintitle">中继器</span>上的<span class="filepath"> Communications.cfg</span>文件，以便可以使用此URI访问事件数据。 请参阅<a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440">监控事件数据空间</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2"><span class="wintitle">中继器</span>的参数，目标<span class="keyword"> Insight Server</span>从中检索事件数据文件。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名称 </td> 
      <td colname="col2">可选。用于标识<span class="wintitle">中继器</span>的名称。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Server Common Name（SSL 服务器通用名称） </td> 
      <td colname="col2">仅当Use SSL（使用SSL）设置为true时，才需要此参数。 存储事件数据的<span class="wintitle">中继器</span>的通用名称。 此名称必须与计算机通信证书中列出的通用名称匹配。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 地址 </td> 
      <td colname="col2">存储事件数据的中继器</span>的主机名或数字IP地址。 <span class="wintitle">服务器的通用名称不是有效的条目。 </span></td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port（端口） </td> 
      <td colname="col2"> 用于数据传输的端口。 默认端口为 80。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
      <td colname="col2">仅当Use SSL（使用SSL）设置为true时，才需要此参数。 用于连接到<span class="wintitle">中继器</span>的许可证证书的名称。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Use SSL（使用 SSL） </td> 
      <td colname="col2"> <p>确定是否使用SSL进行数据传输。 选项为true或false，默认值为false。 </p> <p> <p>注意：不建议使用SSL，因为它可能会对性能产生负面影响。 请注意，除非将<span class="wintitle">中继器</span>连接到目标计算机的网络不安全，否则不需要SSL。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 结束时间、开始时间 </td> 
      <td colname="col2"> <p>（可选）将复制到目标<span class="keyword"> Insight Server</span>的事件数据文件集限制为包含由开始时间和结束时间定义范围内的数据的文件集。 如果设置了“开始时间”，则不会复制所有日志条目都来自早于指定开始时间的事件数据文件。 如果设置了“结束时间”，则不会复制指定时间或以后开始的所有日志条目的事件数据文件。 如果文件中的部分数据在指定范围内，则整个文件将复制到目标计算机。 </p> <p>Adobe 建议使用以下时间格式之一： 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">January 1 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">Jan 1 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：您必须指定时区。 如果未指定，时区不默认为系统时间。 如果您要实施夏令时或类似的时钟调整策略，则必须在Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span>计算机中保存包含相应规则的<span class="filepath"> .dst</span>文件。 有关支持的时区缩写列表以及有关实施夏令时的信息，请参阅<a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211">时区代码</a>。 </p> </p> <p> <p>注意： 要使用这些设置，事件数据文件的名称必须以ISO日期(YYYYMMDD)开头，并且每个文件必须包含从该日期的上午12点开始的24小时期间的数据。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。
   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

此示例说明了如果Flatten Paths（拼合路径）和Recursive（递归）参数均设置为true，如何复制文件。

假定远程URI为[!DNL /RemoteRoot/]，本地路径为 [!DNL E:\LocalRoot\]。 在远程([!DNL Repeater])计算机上，文件的组织方式如下：

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

复制完成后，本地目录具有以下文件：

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

在本地目录中，不会创建子目录，并且远程目录树中的所有文件都放置在本地目录的顶级中。

>[!NOTE]
>
>如果远程计算机上不同子目录中的文件共享相同的名称，则[!DNL Replication Service]可能会停止或发生其他未定义的行为。
