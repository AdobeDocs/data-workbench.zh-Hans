---
description: 访问级别描述允许一组用户在计算机上读取或修改哪些URI。
title: 了解访问级别
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 4%

---

# 了解访问级别{#understanding-access-levels}

访问级别描述允许一组用户在计算机上读取或修改哪些URI。

按照以下准则，根据需要为贵组织的用户定义访问级别：

* 没有尾随斜杠字符的特定URI仅限访问该URI。 例如，[!DNL /Components/Communications.cfg]仅提供对[!DNL Communications.cfg]文件的访问。

* 指定目录的尾随斜杠(/)为群组成员提供对该字符串开头的任何URI的访问权限。 例如， /Profiles/提供对整个Profiles目录的访问。
* 尾随的美元符号符号($)仅限制对确切URI的访问，即使它是目录也是如此。 例如， /Profiles/$提供读取主Profiles目录的权限，但不能读取该目录中的任何文件。

   要访问特定文件，您无需使用尾随$。

   例如，[!DNL /Components/Communications.cfg]和[!DNL /Components/Communications.cfg$]提供相同的访问。

* 百分比符号(%)可与CN（通用名称）一起使用，以允许访问。 例如， /Users/%CN%/允许访问与[!DNL Insight]用户的SSL证书通用名称匹配的User目录。 请注意，此语法在URI中只能使用一次。

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
   <td colname="col4"> <p>对所有<span class="keyword"> Insight Server</span>目录的读取和写入访问权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>传感器 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>对<span class="wintitle">传感器</span>用来与<span class="keyword"> Insight Server</span>通信的两个文件的读取和写入访问权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户 </p> </td> 
   <td colname="col2"> <p>/配置文件/ </p> <p>/状态/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>对与<span class="keyword"> Insight</span>用户的SSL证书通用名称匹配的User目录的读取和写入访问权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高级用户 </p> </td> 
   <td colname="col2"> <p>/配置文件/$ </p> <p>/状态/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> <p>/配置文件/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>高级用户可以与用户具有相同的访问权限，并且添加了写入Profiles目录的功能。 这些用户可以编辑配置文件，并为其他<span class="keyword"> Insight</span>用户启用自动更新的更改，例如在分发新定义的工作区时。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>群集服务器 </p> </td> 
   <td colname="col2"> <p>/处理服务器的组件/ </p> <p>/地址/ </p> <p>/配置文件/ </p> <p>/Lookups/ </p> <p>/访问控制/ </p> <p>/Bin/ </p> <p>/日志/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>对群集目录的读取和写入访问权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报表服务器 </p> </td> 
   <td colname="col2"> <p>/配置文件/$ </p> <p>/状态/ </p> <p>/Software/ </p> <p>/地址/ </p> <p>/用户/$ </p> </td> 
   <td colname="col3"> <p>/配置文件/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>允许报表机器与电源用户具有相同的访问权限，并且还能够写入<span class="filepath"> ReportStatus.vsp</span>文件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**配置访问控制**

在定义访问控制组时，您需要包括所有需要访问此[!DNL Insight Server]计算机的系统管理员、用户、群集服务器和报表服务器用户。 您可以使用IP地址或SSL证书信息（如通用名称或组织）授予访问权限。

>[!NOTE]
>
>当[!DNL Access Control.cfg]文件在[!DNL Insight Server]上发生更改时，所有现有连接都将终止并强制重新连接。 根据更新的[!DNL Access Control.cfg]文件中的权限检查连接。 在“服务器管理器”界面中，[!DNL Insight Server]图标会暂时变为红色，然后再次变为绿色，因为连接已终止，并且必须与所有其他连接一起重新连接。

1. 在[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。

1. 右键单击要配置的[!DNL Insight Server]图标，然后单击&#x200B;**[!UICONTROL Files]**。

1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Access Control]**&#x200B;以查看其内容。 [!DNL Access Control.cfg] 文件位于此目录中。

1. 右键单击&#x200B;*服务器名称*&#x200B;列中[!DNL Access Control.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中会出现[!DNL Access Control.cfg]的复选标记。

1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。

1. 在[!DNL Access Control.cfg]窗口中，单击&#x200B;**[!UICONTROL Access Control Groups]**&#x200B;以查看其内容。

   ![](assets/access_ctrl_cfg.png)

1. 要添加新的访问控制组，请执行以下操作：

   1. 右键单击&#x200B;**[!UICONTROL Access Control Groups]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Group]**。

   1. 右键单击&#x200B;**[!UICONTROL Members]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Member]**。

      未预定义默认组的成员。 默认情况下，将向127.0.0.1（本地主机）授予管理员访问权限，并向IP:*授予[!DNL Sensor]访问权限。 必须定义所有其他访问控制组成员。

   1. 完成参数。

1. 要向现有访问控制组添加新成员，请执行以下操作：

   1. 右键单击相应访问控制组下的&#x200B;**[!UICONTROL Members]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Member]**。

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**&#x200B;保存文件。

1. 要将本地所做的更改保存到[!DNL Insight Server]计算机，请在[!DNL Server Files Manager]列中右键单击[!DNL Temp]列中[!DNL Access Control.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** ***[!UICONTROL server name]**>*。
