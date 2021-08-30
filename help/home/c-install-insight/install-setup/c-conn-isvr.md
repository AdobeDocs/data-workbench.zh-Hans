---
description: 安装 Insight 软件和数字证书之后，必须启动 Insight 并配置它与 Insight Server 的连接。
title: 配置与 Insight Server 的连接
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
exl-id: 6a87e972-069a-435c-9bac-23b20f165ebb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 62%

---

# 配置与 Insight Server 的连接{#configuring-the-connection-to-insight-server}

安装 Insight 软件和数字证书之后，必须启动 Insight 并配置它与 Insight Server 的连接。

>[!NOTE]
>
>在某些情况下，Adobe咨询服务或您的系统管理员可能已预配置了与Insight Server的连接。 如果是这样，则您无需完成此任务。

首次启动 Insight 时，它会自动连接到 Adobe 许可证服务器以注册您的数字证书。若要成功完成注册过程，在执行以下步骤时必须将您的计算机连接到 Internet。

>[!NOTE]
>
>如果您已请求、下载和安装预锁定证书（如[下载和安装数字证书](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9)中所述），则Insight将不会尝试连接到许可证服务器，并且您将不会收到错误。

**配置与 Insight Server** 的连接

当 Insight 运行在群集环境中时，应将其配置为访问主 Insight Server 以避免发生同步问题。在Insight中，您可以使用[服务器管理器](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-svrs-mgr.html)中的[!DNL Related Servers]菜单项查看有关群集中处理[!DNL Insight Servers]的信息。

1. 启动 Insight。
1. 在[!DNL Worktop]上，单击&#x200B;**[!UICONTROL Admin]**，然后单击&#x200B;**[!UICONTROL First Steps]**。

1. 单击&#x200B;**[!UICONTROL Configure Connection to Servers]**&#x200B;缩略图。

   将显示[!DNL Servers Manager]、[!DNL Insight.cfg]文件以及配置[!DNL Insight.cfg]文件的说明。

1. 在[!DNL Insight.cfg]窗口中，右键单击&#x200B;**[!UICONTROL Servers]** ，然后单击&#x200B;**[!UICONTROL Add new child]** > **[!UICONTROL Server]**。

   ![](assets/cfg_Workstation_AddChild.png)

1. 完成或修改服务器参数以便为 Insight 提供对主 Insight Server 的访问权限。有关Insight.cfg文件中参数的详细描述，请参阅[配置参数](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-insght-config-param.html)。

   ![](assets/cfg_Workstation_AddServer.png)

1. 对于要配置连接的每个 Insight Server，重复步骤 4 和步骤 5。
1. 要保存配置更改，请右键单击窗口顶部的&#x200B;**[!UICONTROL Insight.cfg (modified)]** ，然后单击&#x200B;**[!UICONTROL Save as Insight.cfg]**。

   Insight会尝试使用您指定的设置连接到[!DNL Insight Server(s)]。 如果已建立连接，则[!DNL Servers Manager]中会显示一个绿色节点，如下页所示。

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **绿色：**&#x200B;指示与 Insight Server 的连接处于活动状态。
   * **淡红：**&#x200B;指示服务器存在潜在问题，如服务器处理能力耗尽、内存使用率过高或磁盘空间不足。
   * **红色：**&#x200B;指示与 Insight Server 的连接处于非活动状态。

   如果Insight无法使用指定的设置进行连接，则[!DNL Servers Manager]中会显示一个红色节点。 如果发生这种情况，请参阅[连接疑难解答](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b)。

<!--
c_dir_crt_setup.xml
-->

当您选择要使用的配置文件时，会将配置文件信息（包括相关数据以及为该配置文件定义的任何特定工作区或可视化效果）下载到您的计算机。下载每个配置文件时，Insight 会使用该配置文件名称在安装目录中创建一个文件夹。

例如，如果您选择名为 Sales 的配置文件，则会在您的 Insight 目录中显示一个名为 Sales 的文件夹。该文件夹包含在 Sales 配置文件中定义的量度、维度、工作区以及可视化效果。初始加载配置文件之后，脱机工作时便可以使用该配置文件。请参阅[脱机工作和联机工作](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-off-on.html)。

此外，当您首次从 Insight 连接到 Insight Server 时，Insight Server 会在 Insight 安装目录中创建以下目录。

* **[!DNL Trace]目录：** 目录 [!DNL Trace] 内是Insight日志文件( [!DNL insight.log])。当[!DNL Insight.log]文件的大小达到100 MB时，该文件将重命名为[!DNL insight-1.log]。 如果名称为[!DNL insight-1.log]的文件已存在，则会将[!DNL insight-1.log]重命名为[!DNL insight-2.log]等，最大值为[!DNL insight-9.log]。 文件 [!DNL insight.log] 始终包含最新的日志信息，[!DNL insight-max.log] 包含最旧的日志信息。

* **[!DNL User]目录：** 在目录 [!DNL User] 内，有与迄今使用的每个配置文件对应的文件夹，而在每个配置文件文件夹中，都有名为和 [!DNL Work] 的文件夹 [!DNL Workspaces]。目录`User\*profile name*\Workspaces`是保存Insight工作区文件的默认位置。 `User\*profile name*\Work` 是保存Insight可视化图表和Insight用户执行的其他自定义工作的默认位置。

下表列出了经常访问的组件的默认位置。

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 组件 </th> 
   <th colname="col2" class="entry"> 目录位置 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>保存的可视化效果 </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>配置文件名称</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>保存的<span class="wintitle">工作区</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>配置文件名称</i>\Workspaces\<i>选项卡名称</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>保存的 <span class="filepath">.png</span> 文件 </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>配置文件名称</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数据缓存 </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Insight.log</span> 文件 </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

您可以按键名称、键类型或值进行搜索以便快速找到某个条目，避免以滚动方式在展开的大型文件中查找嵌套信息。您可以查找到维度名称、服务器名称等。以下示例显示了短语 map 搜索的匹配项。

![](assets/cfg_search.PNG)

在此字段中键入一个搜索短语以查找数据。根据是否匹配成功，字段的颜色将会发生相应变化。匹配项将会突出显示，而非匹配项将会变暗。如果不存在匹配项，则搜索字段的背景将会变为红色。当您按 Enter 时，配置树将展开每个存在匹配项的位置，并折叠不存在匹配项的位置。

您还可以在 [!DNL Search] 字段中使用正则表达式。例如，您可以使用：[!DNL *zip.*]&#x200B;适用于包含“zip”字样的任何条目。

若要清除搜索，请按 **[!UICONTROL Escape]**。
