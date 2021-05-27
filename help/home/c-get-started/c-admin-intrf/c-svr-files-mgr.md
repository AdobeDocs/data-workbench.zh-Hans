---
description: “服务器文件管理器”允许您从任何授权Data Workbench远程管理Data Workbench服务器计算机，方法是提供对产品安装目录中所有目录和文件（包括配置和查找文件）的访问。
title: 服务器文件管理器
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 55%

---

# 服务器文件管理器{#server-files-manager}

“服务器文件管理器”允许您从任何授权Data Workbench远程管理Data Workbench服务器计算机，方法是提供对产品安装目录中所有目录和文件（包括配置和查找文件）的访问。

您可以使用[!DNL Admin]菜单访问[!DNL Server Files Manager]，也可以右键单击[!DNL Servers Manager]中Data Workbench服务器计算机的节点，然后单击&#x200B;**[!UICONTROL Server Files]**。

![](assets/vis_FileManager.png)

>[!NOTE]
>
>您可以创建显示选定目录的新服务器文件管理器。 请参阅[创建新服务器文件管理器](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816)。

[!DNL Server Files Manager]的左列列出了文件和文件夹名称。 中间和右侧列中的复选标记指示这些目录和文件在文件结构中所处的位置。

如果文件位于产品的安装目录中，则&#x200B;*服务器名称*(例如，Data Workbench服务器)列包含复选标记。 如果文件位于&#x200B;*Data Workbench安装目录*\Temp目录的Data Workbench用户计算机上，则[!DNL Temp]列包含复选标记。 复选标记的颜色指示位于不同位置的文件是否是在同时修改的。

* 服务器名称列中的红色复选标记表示文件夹或文件位于Data Workbench服务器计算机上。
* [!DNL Temp]列中的红色复选标记表示文件或文件夹的本地副本与Data Workbench服务器计算机上的文件或文件夹具有相同的修改日期和时间。
* [!DNL Temp]列中的白色复选标记表示&#x200B;*Data Workbench安装目录*\Temp目录中的文件或文件夹与Data Workbench服务器计算机上的文件或文件夹具有不同的修改日期和时间。

下图显示了同时带有红色和白色复选标记的[!DNL Server Files Manager]:

![](assets/vis_FileManager_RedWhiteChecks.png)

**使用[!DNL Server Files Manager]**

您可以使用[!DNL Server Files Manager]在Data Workbench服务器计算机上处理目录和文件。

下表列出了可使用[!DNL Server Files Manager]完成的任务：

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 若要执行此任务... </th> 
   <th colname="col2" class="entry"> 执行此操作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>查看任意目录内的文件 </p> </td> 
   <td colname="col2"> <p>单击要查看其内容的目录名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>隐藏目录的内容 </p> </td> 
   <td colname="col2"> <p>单击目录名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看有关目录的详细信息 </p> </td> 
   <td colname="col2"> <p>右键单击目录旁边服务器名称或“<span class="wintitle">临时</span>”列中的单元格。会看到以下信息： </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">路径. 目录的路径。 </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">目录。目录的名称。 </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">From. 目录的位置，“远程”还是“临时”。 </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">日期（仅“临时”列）。本地副本的创建日期或上一次修订日期。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看有关文件的详细信息 </p> </td> 
   <td colname="col2"> <p>右键单击文件旁边服务器名称或“<span class="wintitle">临时</span>”列中的复选标记。会看到以下信息： </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">路径. 文件的路径。 </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">文件. 文件的名称 </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">从。 目录的位置，“远程”还是“临时”。 </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">日期. 文件上一次修订的日期。 </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">大小. 文件的大小。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将目录下载到本地计算机 </p> </td> 
   <td colname="col2"> <p>右键单击<i>服务器名称</i>列中该目录的复选标记，然后单击<span class="uicontrol">制作目录本地副本</span>。“<span class="wintitle">临时</span>”列中会出现该目录的复选标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将文件下载到本地计算机 </p> </td> 
   <td colname="col2"> <p>右键单击<i>服务器名称</i>列中该文件的复选标记，然后单击<span class="uicontrol">制作本地副本</span>。“<span class="wintitle">临时</span>”列中会出现该文件的复选标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将日志文件的最后一部分下载到本地计算机 </p> </td> 
   <td colname="col2"> <p>为了避免下载整个日志文件（尤其是当您知道错误消息接近文件结尾时），请右键单击服务器名称列中该文件的复选标记，然后单击<span class="uicontrol">截去尾部</span>并选择要下载部分的大小。“<span class="wintitle">临时</span>”列中会出现该文件的复选标记。本地文件只包含指定的数据量（从文件结尾开始）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>打开目录 </p> </td> 
   <td colname="col2"> <p>右键单击“<span class="wintitle">临时</span>”列中目录的复选标记，然后单击<span class="uicontrol">打开</span> &gt; <span class="uicontrol">文件夹</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>打开文件 </p> </td> 
   <td colname="col2"> <p>右键单击<span class="wintitle">临时</span>列中文件的复选标记，单击<span class="uicontrol">打开</span>，然后单击<span class="uicontrol">Data Workbench</span>、<span class="uicontrol">在记事本</span>中或<span class="uicontrol">文件夹</span>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将目录的本地副本保存到Data Workbench服务器 </p> </td> 
   <td colname="col2"> <p>右键单击“<span class="wintitle">临时</span>”列中目录的复选标记，然后单击<span class="uicontrol">保存目录到</span> &gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将文件的本地副本保存到Data Workbench服务器 </p> </td> 
   <td colname="col2"> <p>右键单击“<span class="wintitle">临时</span>”列中文件的复选标记，然后单击<span class="uicontrol">保存到</span> &gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>删除目录或文件的本地副本 </p> </td> 
   <td colname="col2"> <p>右键单击“<span class="wintitle">临时</span>”列中目录或文件的复选标记，然后单击<span class="uicontrol">删除</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在Microsoft Outlook中将文件复制并粘贴为电子邮件附件 </p> </td> 
   <td colname="col2"> <p>右键单击“<span class="wintitle">临时</span>”列中文件的复选标记，然后单击<span class="uicontrol">复制</span>。在电子邮件正文中，按 Ctrl+v 附加该文件。 </p> </td> 
  </tr> 
 </tbody> 
</table>
