---
description: 系统管理员使用的主要工具是“服务器管理器”。
title: 服务器管理器
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 41%

---

# 服务器管理器{#servers-manager}

{{eol}}

系统管理员使用的主要工具是“服务器管理器”。

它是确定整体系统状态及执行系统配置、文件管理及错误监视功能的主界面。

“服务器管理器”为每个Data Workbench服务器显示一个彩色圆点（节点）， [!DNL Sensor] 安装，并为每个安装提供一目了然的系统状态。 它还会显示一个用于Data Workbench安装的节点。

绿色节点表示活动连接，红色节点表示被禁用或不可访问的连接，灰色节点表示状态不确定的连接。

![](assets/vis_SysStat_RedGreenDots.png)

右键单击某个节点可显示有关连接组件的信息，并提供对任意相关菜单的访问权限。

下表描述了在右键单击Data Workbench节点、Data Workbench服务器(包括群集中的主控Data Workbench服务器)或 [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>产品 </p> </td> 
   <td colname="col2"> <p>产品名称、版本、内部版本号。 </p> <p>示例：Data Workbench5.3(00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>Data Workbench计算机的IP地址。 </p> <p>例如：100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>配置 </p> </td> 
   <td colname="col2"> <p>指向 <span class="keyword"> Data Workbench </span> 配置文件。 单击 <span class="uicontrol"> 配置 </span> &gt; <span class="uicontrol"> Insight.cfg </span> 以显示Data Workbench配置窗口。 在此窗口中进行并保存的任何更改都会反映在 <span class="filepath"> Insight.cfg </span> 文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>产品 </p> </td> 
   <td colname="col2"> <p>产品名称、版本、内部版本号。 </p> <p>示例：Data Workbench服务器5.3(00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Data Workbench服务器计算机的通用名称。 </p> <p>示例：<span class="filepath">myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>服务器的 IP 地址或完全限定域名，在计算机上的“地址”文件中和 <span class="filepath">Insight.cfg</span> 文件的 Network Location（网络位置）参数中配置。 </p> <p>例如：100.0.0.1 </p> <p>有关“地址”文件的信息，请参阅《服务器产品安装和管理指南》<i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>状态 </p> </td> 
   <td colname="col2"> <p>Data Workbench服务器的当前状态。 当Data Workbench服务器正常运行时，此字段显示“确定”。 如果发生错误且Data Workbench服务器节点为红色，则字段会显示错误（例如，“403禁止访问”）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>详细状态 </p> </td> 
   <td colname="col2"> <p>指向的链接 <span class="keyword"> Data Workbench服务器 </span> <span class="wintitle"> 详细状态 </span> 界面，用于对Data Workbench服务器的错误或其他问题进行故障诊断。 </p> <p>有关更多信息，请参阅 <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> 详细状态界面</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>远程桌面 </p> </td> 
   <td colname="col2"> <p>打开 <span class="wintitle"> 远程桌面 </span> 会话到Data Workbench服务器计算机。 </p> <p>有关更多信息，请参阅 <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> 远程桌面选项 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>服务器文件 </p> </td> 
   <td colname="col2"> <p>指向的链接 <span class="wintitle"> 服务器文件管理器 </span>，显示Data Workbench服务器安装目录中的目录和文件。 </p> <p>有关更多信息，请参阅 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> 服务器文件管理器 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>服务器监视器 </p> </td> 
   <td colname="col2"> <p><span class="wintitle">服务器监视器</span>界面的链接，可用于疑难排解或跟踪性能参数。 </p> <p>有关更多信息，请参阅 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> 服务器监视器界面 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>相关服务器 </p> </td> 
   <td colname="col2"> <p>仅用于Data Workbench服务器群集。 </p> <p>列出主控中所列计算机的通用名称的菜单 <span class="filepath"> Data Workbench服务器的*.address </span> 文件。 此列表通常包含所有处理 <span class="keyword"> Data Workbench服务器 </span> 在群集中。 仅当Data Workbench具有主控的副本时，才会显示此菜单 <span class="filepath"> Data Workbench服务器的*.address </span> 文件。 </p> <p>单击<span class="uicontrol">相关服务器</span>后，即可单击以下任意选项： 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> 服务器监视器列表</span>，显示列出所有相关服务器详细信息的<span class="wintitle">服务器监视器</span>界面 </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">任何Data Workbench服务器的通用名称，它显示一个上下文菜单，用于打开该特定服务器的以下任意内容： 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol">详细状态</span>。请参阅 <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> 详细状态界面 </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol">远程桌面</span>。请参阅 <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> 远程桌面选项 </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> 服务器文件管理器 </span>. 请参阅 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> 服务器文件管理器 </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol">服务器监视器</span>。请参阅 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> 服务器监视器界面 </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>产品 </p> </td> 
   <td colname="col2"> <p>产品名称、版本、内部版本号。 </p> <p>示例：传感器 3.76; J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> 在此安装的<span class="wintitle">传感器</span>配置文件中指定的<span class="wintitle">传感器</span> ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>安装有<span class="wintitle">传感器</span>的 Web 或应用程序服务器的 IP 地址。 </p> <p>例如：100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>由操作系统分配的进程 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>是否 <span class="wintitle"> 传感器 </span> Data Workbench服务器使用SSL进行通信。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>时间 </p> </td> 
   <td colname="col2"> <p>时间 (HH):MM:SS) <span class="wintitle"> 传感器 </span> 上次与Data Workbench服务器建立连接。 </p> </td> 
  </tr> 
 </tbody> 
</table>
