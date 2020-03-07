---
description: 在 Worktop 中，您可以组织和访问所有工作区和报表。
solution: Analytics
title: Worktops
topic: Data workbench
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Worktops{#worktops}

在 Worktop 中，您可以组织和访问所有工作区和报表。

In most cases, the [!DNL Worktop] is displayed immediately after you open Data Workbench. [!DNL Worktop] 的功能包括侧栏和选项卡式界面。此外，您还可以使用侧栏添加可视化和访问常用的功能。

**Worktop**

![](assets/client-wktp.png)

The [!DNL Worktop] also enables you to create and save new and updated workspaces and reports, as well as publish workspaces and reports to the Data Workbench server for others to access.

The [!DNL Worktop] elements table below describes each element of the [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> 侧栏 </td> 
   <td colname="col2"> <p>侧栏提供工作区的上下文和控件，并感知工作区的当前状态以及对常用功能的访问。侧栏中可用的功能如下： </p> <p> <b>连接：</b>显示联机状态的状态指示器。单击连接状态可启用或禁用“<span class="wintitle">联机工作</span>”。See <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Working Offline and Online</a>. </p> <p> <b>配置文件：</b>当前正在使用的配置文件的指示器。 </p> <p> <b>截至：</b>显示配置文件的数据集中数据最新程度的状态指示器。将从 DPU 服务器下载并处理该数据，此过程仅在联机工作时才会发生。 </p> <p> <b>查询/采样置信度：</b>查询完成的指示器。当状态查询到 100% 时，表示已查询所有数据。 </p> <p> <b>添加：</b>允许您向侧栏中添加面板、图例和表格等可视化。请参阅<a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06">向侧栏中添加可视化</a>。 </p> <p> <b>选项：</b>允许您还原到之前的侧栏设置和自动隐藏侧栏。 </p> <p>Sidebar settings are saved in the <span class="filepath"> sidebar.vw</span> file when you close Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>选项卡和子选项卡或下拉子目录（不显示） </p> </td> 
   <td colname="col2"> <p>Each tab that appears on the <span class="wintitle"> Worktop</span> corresponds to the tab’s <i>working profile name</i>\Workspaces\<i>tab name</i> folder within the Data Workbench installation directory and represents a particular type of information, such as Dashboards, Activity, Acquisition, Visitors, and so on. 默认情况下，选项卡名称文件夹中的子文件夹会显示为子选项卡，但也可显示为子目录。请参阅 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> 自定义 Worktop 选项卡</a>. </p> <p> <p>注意： 每个Data Workbench配置文件都提供一组标准选项卡。 由于您可以完全自定义实施，因此显示的工作区（以及选项卡）可能与本指南中所述的内容有所不同。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件状态 </td> 
   <td colname="col2"> 提供与Data Workbench Server的连接状态以及当前加载的配置文件的名称。 配置文件数据集中数据的“截至”日期和时间显示在联机指示器下。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小化、最大化、关闭 </td> 
   <td colname="col2"> 标准 Windows 功能。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 缩略图 </td> 
   <td colname="col2"> <p>缩略图是 <span class="wintitle">Worktop</span> 上显示的工作区的快照。每次保存工作区时获取新快照。使用缩略图，可以快速识别 <span class="wintitle">Worktop</span> 上的特定工作区。 </p> <p>若要打开工作区，请单击缩略图。 </p> <p> <p>注意： 每个Data Workbench配置文件都提供一组标准工作区。 由于您可以完全自定义实施，因此显示的工作区（以及缩略图）可能与本指南中所述的内容有所不同。 </p> </p> <p>有关工作区的详细信息，请参阅 <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> 配置侧栏</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误消息 </td> 
   <td colname="col2"> <p>错误消息以红色显示在状态下面。有关状态代码描述，请参阅 <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external">http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>。 </p> <p>例如：403_Forbidden。 </p> </td> 
  </tr> 
 </tbody> 
</table>
