---
description: 访问级别描述允许一组用户读取或修改计算机上的哪些URI。
solution: Analytics
title: 了解访问级别
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 4%

---


# 了解访问级别{#understanding-access-levels}

访问级别描述允许一组用户读取或修改计算机上的哪些URI。

按照以下准则为组织的用户定义所需的访问级别：

* 没有尾随斜杠字符的特定URI仅限访问该URI。 例如， [!DNL /Components/Communications.cfg] 仅提供对文 [!DNL Communications.cfg]件的访问。

* 指定目录的尾部斜杠(/)允许组成员访问以该字符串开头的任何URI。 例如， /用户档案/提供对整个用户档案目录的访问。
* 尾随美元符号($)仅限于访问精确的URI，即使它是目录也是如此。 例如，/用户档案/$提供读取主用户档案目录的权限，但不能读取该目录中的任何文件。

   要访问特定文件，您无需使用尾随$。

   例如， [!DNL /Components/Communications.cfg] 并提 [!DNL /Components/Communications.cfg$] 供相同的访问。

* 百分比符号(%)可与CN（公用名称）一起使用以允许访问。 例如，/Users/%CN%/允许访问与用户的SSL证书公用名称匹配的用户目 [!DNL Insight] 录。 请注意，此语法在URI中只能使用一次。

预定义访问控制组中的URI已配置如下：

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 群组名称 </th> 
   <th colname="col2" class="entry"> 只读访问 </th> 
   <th colname="col3" class="entry"> 读写访问 </th> 
   <th colname="col4" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>管理员 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>对所有Insight Server目录的读 <span class="keyword"> 写访问</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>传感器 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>对传感器用来与Insight Server通信的两 <span class="wintitle"> 个文</span> 件的读 <span class="keyword"> 写访问权</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户 </p> </td> 
   <td colname="col2"> <p>/配置文件/ </p> <p>/状态/ </p> <p>/软件/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>对与Insight用户的SSL证书公用名称匹配的用户目录的读写 <span class="keyword"> 访问</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高级用户 </p> </td> 
   <td colname="col2"> <p>/配置文件/$ </p> <p>/状态/ </p> <p>/软件/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> <p>/配置文件/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Power Users与Users具有相同的访问权限，并添加了写入用户档案目录的功能。 这些用户可以编辑用户档案，并启用其他Insight用户的自动更新 <span class="keyword"> 功能</span> ，例如在分发新定义的工作区时。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>群集服务器 </p> </td> 
   <td colname="col2"> <p>/用于处理服务器的组件/ </p> <p>/地址/ </p> <p>/配置文件/ </p> <p>/Lookups/ </p> <p>/访问控制/ </p> <p>/Bin/ </p> <p>/日志/ </p> </td> 
   <td colname="col3"> <p>/群集/ </p> </td> 
   <td colname="col4"> <p>对群集目录的读和写访问。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报表服务器 </p> </td> 
   <td colname="col2"> <p>/配置文件/$ </p> <p>/状态/ </p> <p>/软件/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> <p>/配置文件/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>允许报表计算机与高级用户具有相同的访问权限，并增加了写入ReportStatus. <span class="filepath"> vsp文件的功能</span> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**配置访问控制**

定义访问控制组时，需要包括需要访问此计算机的所有系统管理员、用户、群集服务器和报告服务器 [!DNL Insight Server] 用户。 您可以使用IP地址或SSL证书信息（如通用名称或组织）授予访问权限。

>[!NOTE]
>
>打开文 [!DNL Access Control.cfg] 件时，所有现 [!DNL Insight Server]有连接都将终止并强制重新连接。 根据更新文件中的权限检查 [!DNL Access Control.cfg] 连接。 在服务器管理器界面中，该图 [!DNL Insight Server] 标会暂时变为红色，然后再次变为绿色，因为连接已终止，并且必须与所有其他连接一起重新连接。

1. 在>选 [!DNL Admin] 项 [!DNL Dataset and Profile] 卡上，单击缩略图 **[!UICONTROL Servers Manager]** 以打开服务器管理器工作区。

1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Files]**。

1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Access Control]** 以视图其内容。 [!DNL Access Control.cfg] 文件位于此目录中。

1. Right-click the check mark in the *server name* column for [!DNL Access Control.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Access Control.cfg].

1. 右键单击列中新创建的复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。

1. 在窗口 [!DNL Access Control.cfg] 中，单击 **[!UICONTROL Access Control Groups]** 以视图其内容。

   ![](assets/access_ctrl_cfg.png)

1. 添加新访问控制组：

   1. 右键单 **[!UICONTROL Access Control Groups]** 击，然 **[!UICONTROL Add new]** 后单击 **[!UICONTROL Group]**>。

   1. 右键单 **[!UICONTROL Members]** 击，然 **[!UICONTROL Add new]** 后单击 **[!UICONTROL Member]**>。

      默认组的成员未预定义。 默认情况下，管理员访问权限将授予127.0.0.1（本地主机）, [!DNL Sensor] 并且访问权限将授予IP:*。 必须定义所有其他访问控制组成员。

   1. 完成参数。

1. 要向现有访问控制组添加新成员，请执行以下操作：

   1. 右键单击 **[!UICONTROL Members]** 相应访问控制组下的，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Member]**。

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and then clicking **[!UICONTROL Save]**.

1. 要保存对计算机进行的本 [!DNL Insight Server] 地更改， [!DNL Server Files Manager]请在列中右键单击对 [!DNL Access Control.cfg] 勾标记，然后 [!DNL Temp] 单击&lt; **[!UICONTROL Save to]*****[!UICONTROL server name]***>。

