---
description: 访问级别描述允许一组用户读取或修改计算机上的哪些URI。
solution: Insight
title: 了解访问级别
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解访问级别{#understanding-access-levels}

访问级别描述允许一组用户读取或修改计算机上的哪些URI。

按照以下准则为贵组织的用户定义所需的访问级别：

* 没有尾部斜杠字符的特定URI仅限访问该URI。 例如，仅 [!DNL /Components/Communications.cfg] 允许访问 [!DNL Communications.cfg]文件。

* 指定目录的尾部斜杠(/)允许用户组成员访问以该字符串开头的任何URI。 例如，/Profiles/提供对整个Profiles目录的访问。
* 尾部美元符号($)仅限制对精确URI的访问，即使它是目录也是如此。 例如，/Profiles/$提供读取主Profiles目录的权限，但不能读取该目录中的任何文件。

   要访问特定文件，您无需使用尾部$。

   例如，并 [!DNL /Components/Communications.cfg] 提供 [!DNL /Components/Communications.cfg$] 相同的访问权限。

* 百分比符号(%)可与CN（通用名称）一起使用以允许访问。 例如，/Users/%CN%/允许访问与用户的SSL证书公用名称匹配的用户目 [!DNL Insight] 录。 请注意，此语法在URI中只能使用一次。

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
   <td colname="col4"> <p>对传感器用来与Insight Server通信的两 <span class="wintitle"> 个文件</span> ，进行读写 <span class="keyword"> 访问</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户 </p> </td> 
   <td colname="col2"> <p>/配置文件/ </p> <p>/状态/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>对与Insight用户的SSL证书公用名匹配的用户目录的读写 <span class="keyword"> 访问</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高级用户 </p> </td> 
   <td colname="col2"> <p>/配置文件/$ </p> <p>/状态/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> <p>/配置文件/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>高级用户可以与用户具有相同的访问权限，并且添加了写入Profiles目录的功能。 这些用户可以编辑配置文件，并使更改能够自动更新为其他 <span class="keyword"> Insight</span> 用户，例如在分发新定义的工作区时。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>群集服务器 </p> </td> 
   <td colname="col2"> <p>/处理服务器组件/ </p> <p>/地址/ </p> <p>/配置文件/ </p> <p>/Lookups/ </p> <p>/访问控制/ </p> <p>/Bin/ </p> <p>/日志/ </p> </td> 
   <td colname="col3"> <p>/群集/ </p> </td> 
   <td colname="col4"> <p>对群集目录的读和写访问。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报告服务器 </p> </td> 
   <td colname="col2"> <p>/配置文件/$ </p> <p>/状态/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> <p>/配置文件/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>允许报告计算机与高级用户具有相同的访问权限，并增加了对 <span class="filepath"> ReportStatus.vsp文件的写入功能</span> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**配置访问控制**

在定义访问控制组时，您需要包括所有需要访问此计算机的系统管理员、用户、群集服务器和报告服务器用 [!DNL Insight Server] 户。 您可以使用IP地址或SSL证书信息（如公用名称或组织）授予访问权限。

>[!NOTE]
>
>打开文 [!DNL Access Control.cfg] 件更改后，所有现 [!DNL Insight Server]有连接都将终止并强制重新连接。 根据更新后的文件中的权限检查连 [!DNL Access Control.cfg] 接。 在“服务器管理器”界面中，该图 [!DNL Insight Server] 标会临时变为红色，然后再次变为绿色，因为连接会终止，并且会强制与所有其他连接一起重新连接。

1. 在>选 [!DNL Admin] 项卡 [!DNL Dataset and Profile] 上，单击缩略图以 **[!UICONTROL Servers Manager]** 打开Servers Manager工作区。

1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Files]**。

1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Access Control]** 查看其内容。 [!DNL Access Control.cfg] 文件位于此目录中。

1. Right-click the check mark in the *server name* column for [!DNL Access Control.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Access Control.cfg].

1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。

1. 在窗 [!DNL Access Control.cfg] 口中，单 **[!UICONTROL Access Control Groups]** 击以查看其内容。

   ![](assets/access_ctrl_cfg.png)

1. 要添加新的访问控制组，请执行以下操作：

   1. 右键单击 **[!UICONTROL Access Control Groups]** 并单击 **[!UICONTROL Add new]** > **[!UICONTROL Group]**。

   1. 右键单击 **[!UICONTROL Members]** 并单击 **[!UICONTROL Add new]** > **[!UICONTROL Member]**。

      默认用户组的成员未预定义。 默认情况下，管理员访问权限将授予127.0.0.1（本地主机）, [!DNL Sensor] 而访问权限将授予IP:*。 必须定义所有其他访问控制组成员。

   1. 完成参数。

1. 要向现有访问控制组添加新成员，请执行以下操作：

   1. 右键单击相 **[!UICONTROL Members]** 应的访问控制组下的，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Member]**。

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and then clicking **[!UICONTROL Save]**.

1. 要保存对计算机进行的本地更 [!DNL Insight Server] 改，请在 [!DNL Server Files Manager]中右键单击列中的复选 [!DNL Access Control.cfg] 标记，然后单 [!DNL Temp] 击 **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]***>。

