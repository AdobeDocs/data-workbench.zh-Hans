---
description: “详细状态”界面可用于对Data Workbench Server计算机的错误或其他问题进行疑难解答。
solution: Analytics
title: 详细状态界面
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Detailed Status interface{#detailed-status-interface}

“详细状态”界面可用于对Data Workbench Server计算机的错误或其他问题进行疑难解答。

这包括在这 [!DNL Transform] 些计算机或作为Data Workbench Server客户端的 [!DNL Report] 计算机上运行的任何配置文件。 您可以通过菜 [!DNL Master Server] 单访 [!DNL Query Server Detailed Status] 问界面和 [!DNL Admin] 界面。 To access the [!DNL Detailed Status] interface for other computers, in the [!DNL Servers Manager], right-click the node of the server for which you want to view status and click **[!UICONTROL Detailed Status]**. See [The Servers Manager](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

For more information about the Data Workbench server, see the *Server Products Installation and Administration Guide*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>要更新界面中的 [!DNL Detailed Status] 信息，请右键单击标 **[!UICONTROL Detailed Status]** 题并单击 **[!UICONTROL Refresh]**。

The following table lists the tasks that can be completed using the [!DNL Detailed Status] interface.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 若要执行此任务... </th> 
   <th colname="col2" class="entry"> 执行此操作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>显示每个计算机组件及其当前状态 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Component Status（组件状态）</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>显示计算机上的内存使用量 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Memory Status（内存状态）</span>&gt; <span class="uicontrol">Address Space Load（地址空间负载）</span>。 </p> <p>有关监视地址空间负载的详细信息，请参阅《服务器产品安装和管理指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>确定计算机是否配置为使用 /3GB 开关 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Memory Status（内存状态）</span>&gt; <span class="uicontrol">Process Address Space（进程地址空间）</span>。 </p> <p>如果 <span class="wintitle">Total</span>（总量）字段显示的值大于 3000000 KB，则表示您的计算机已配置为使用 /3GB 开关。 </p> <p>有关 /3GB 开关的详细信息，请参阅《服务器产品安装和管理指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>监视用于存储每个维度及其元素名称的磁盘空间和内存量 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Performance（性能）</span>&gt; <span class="uicontrol">Dimensions（维度）</span>&gt; <span class="uicontrol">Disk Usage（磁盘使用情况）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt; </i>或 <span class="uicontrol">Performance（性能）</span>&gt; <span class="uicontrol">Dimensions（维度）</span>&gt; <span class="uicontrol">Memory Usage（内存使用情况）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i>。 </p> <p><span class="wintitle">Disk Usage（磁盘使用情况）</span>字段提供存储每个维度所需要的名称及磁盘空间容量（以 MB 为单位）。较大的磁盘使用量可能会对查询时间产生不利影响，因为Data Workbench服务器必须读取所有数据才能完成相关查询。 降低维度的磁盘使用量可缩短完成相关查询所花费的时间。 </p> <p><span class="wintitle">Memory Usage（内存使用情况）</span>字段提供每个维度中的元素数量以及存储元素名称列表所需的内存量。大量元素可能会对查询期间使用的内存量产生不利影响，因为Data Workbench服务器必须读取每个元素。 降低维度中的元素数量可缩短完成相关查询所花费的时间。 </p> <p>示例：<code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>监视日志处理和转换中各阶段的 CPU 使用率 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Performance（性能）</span>&gt; <span class="uicontrol">CPU Usage（CPU 使用率）</span>&gt; <span class="uicontrol">Log Processing（日志处理）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i> 或 <span class="uicontrol">Performance（性能）</span>&gt; <span class="uicontrol">CPU Usage（CPU 使用率）</span>&gt; <span class="uicontrol">Transformation（转换）</span>&gt; &lt;<span class="uicontrol">配置文件名称</span>&gt;。 </p> <p>这其中的每一组字段都为您提供了日志处理和转换中每个阶段的 CPU 使用率（以秒为单位）。 </p> <p>示例：<code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>完成查询所花费的时间通常与所有维度的总大小成正比。在查看每个维度的大小之后，可以评估特定维度的作用和使用频度是否足以证明维度的性能成本的合理性。如果不能证明，则可以在“<span class="wintitle">配置文件管理器</span>”中删除该维度。请参阅<a href="../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-prof-mgr.md"> Profile Manager</a>。 </p> <p>元素名称列表过大（即大于 128 MB）的维度可能导致“内存不足”错误，即使总地址空间使用量还未达到限制也是如此。 </p> <p>此外，如果您使用的是Data Workbench服务器群集，但没有使用集中标准化，则元素名称列表较大的维会对发送内存预算产生重大影响。 有关集中标准化的详细信息，请参阅《数据集配置指南》<i></i>。如果对于群集中所有服务器，用于存储所有元素名称列表所需的内存量加起来超过 100 MB，则即使在查询活动不多的情况下也可能会收到“已超出发送内存预算”错误消息。例如，如果您有一个四服务器群集，每个服务器上用于存储元素名称列表的内在量超过 25 MB，则可能收到错误消息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>监视日志处理和转换所花费的时间 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Performance（性能）</span>&gt; <span class="uicontrol">CPU Usage（CPU 使用率）</span>&gt; <span class="uicontrol">Log Processing（日志处理）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i> 或 <span class="uicontrol">Performance（性能）</span>&gt; <span class="uicontrol">CPU Usage（CPU 使用率）</span>&gt; <span class="uicontrol">Transformation（转换）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i>。 </p> <p>通过查看这些部分的字段，可以识别可能对日志处理和转换所需时间造成负面影响的过滤器和转换。然后，可以就需要较长处理时间的单个处理器和转换作出相关的设计决策。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>监视磁盘空间使用情况并提高查询速度 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Performance（性能）</span>&gt; <span class="uicontrol">Log Processing Fields（日志处理字段）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i>。 </p> <p>此部分的每个行项目都对应 <span class="filepath">Log Processing.cfg</span> 文件中的一个参数。通过查看这些字段，可以了解每个参数使用的内存量。然后，可以就非常大的单个项目作出相关设计决策。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>确定上一次重新处理或转换所耗费的时间 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Processing Status（处理状态）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i> &gt; <span class="uicontrol">Processing Mode History（处理模式历史记录）</span>。 </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">实时- Data Workbench Server可用于进行查询的时间。 </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Fast Input（快速输入）- 该时间加上“快速合并”时间即是处理数据集所需的总时间。 </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fast Merge（快速合并）- 转换数据集所需的总时间。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>诊断“截至时间”问题 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Processing Status（处理状态）</span>&gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i> &gt; <span class="uicontrol">As Of Time（截至时间）</span>&gt; <span class="uicontrol">Sources as-of（源截至时间）</span>。 </p> <p>通过查看每个源的截至时间，可帮助您确定哪些源会对总截至时间造成不利影响。然后，可以解决与这些特定源有关的问题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>估计运行查询完成要花费多长时间 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Execution Engine（执行引擎）</span>。 </p> <p>查看 <span class="wintitle">Data Sweep Time（数据扫描时间）</span>字段可为您提供查询完成所花时间的估计值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>列出此计算机上所有可用的配置文件及其相关状态的详细信息 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Profiles（配置文件）</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看复制状态 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Component Status（组件状态）</span>。 </p> <p>检查复制组件的状态。如果复制正在运行，即会显示正常。如果复制组件失败，则显示一条错误消息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>To view <span class="wintitle"> Report Server</span> status for a <span class="keyword"> Report</span> computer that connects to the Data Workbench server </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Report Server Status（报表服务器状态）</span>。 </p> <p><span class="wintitle">详细状态</span>界面的这一部分包含 <span class="filepath">Report Server.cfg</span> 文件的副本、有关正在运行的报表数量的信息（当前片段），以及有关最近错误的信息（上一个错误）。 </p> <p>有关编辑 <span class="filepath">Report Server.cfg</span> 文件的步骤，请参阅《Data Workbench 报表指南<i></i>》。 </p> <p> <p>Note: If the <span class="wintitle"> Report Server Status</span> section does not appear in the <span class="wintitle"> Detailed Status</span> interface, you may need to configure the Data Workbench server to display <span class="wintitle"> Report Server Status</span>. 有关步骤，请参阅《Data Workbench 报表指南<i></i>》。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看转换的内存使用信息 </p> </td> 
   <td colname="col2"> <p>单击 <span class="uicontrol">Processing Status（处理状态）</span>&gt; <span class="uicontrol">Transform（转换）</span>。 </p> <p>有关转换的详细信息，请参阅《服务器产品安装和管理指南》<i></i>以及《数据集配置指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将<span class="wintitle">详细状态</span>界面另存为可在文本编辑器（如记事本）中打开或可分发给其他人的 <span class="filepath">*.cfg</span> 文件 </p> </td> 
   <td colname="col2"> <p>右键单击<span class="uicontrol">详细状态</span>标题，然后单击<span class="uicontrol">副本另存为</span>。 </p> <p>注释:  <p>右键单击<span class="uicontrol">详细状态</span>标题并单击<span class="uicontrol">保存到<i>服务器名称</i>/Status/</span> 在<span class="wintitle">详细状态</span>界面中不起作用。将显示以下错误消息： </p> <p>无法保存 /Status/。403 禁止访问 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看<span class="uicontrol">每个日志源的行数</span>量度 </p> </td> 
   <td colname="col2"> <p>如果需要在“详细状态”中报告“每日志源的行数”量度，则Data Workbench管理员应定义“日志源ID”，并在自定义配置文件的Log Processing.cfg中提供唯一的名称。 </p> </td> 
  </tr> 
 </tbody> 
</table>

