---
description: 服务器文件管理器允许您通过提供对产品安装目录中所有目录和文件（包括配置和查找文件）的访问，从任何授权的Data Workbench远程管理和管理Data Workbench服务器计算机。
solution: Analytics
title: 服务器文件管理器
topic: Data workbench
uuid: 62625b9d-587f-4a78-8328-2270869909f8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server Files Manager{#server-files-manager}

服务器文件管理器允许您通过提供对产品安装目录中所有目录和文件（包括配置和查找文件）的访问，从任何授权的Data Workbench远程管理和管理Data Workbench服务器计算机。

您可以使用菜 [!DNL Server Files Manager] 单访 [!DNL Admin] 问，也可以在中右键单击Data Workbench Server计算机的节点并单击 [!DNL Servers Manager] 该节点 **[!UICONTROL Server Files]**。

![](assets/vis_FileManager.png)

>[!NOTE]
>
>您可以创建显示选定目录的新服务器文件管理器。 See [Creating New Server Files Managers](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

列出文件和文 [!DNL Server Files Manager] 件夹名称的左列。 中间和右侧列中的复选标记指示这些目录和文件在文件结构中所处的位置。

If a file resides in the product’s installation directory, the *server name* (for example, Data Workbench server) column contains a check mark. If a file resides on the Data Workbench user’s computer in the *Data Workbench installation directory*\Temp directory, the [!DNL Temp] column contains a check mark. 复选标记的颜色指示位于不同位置的文件是否是在同时修改的。

* 服务器名称列中的红色复选标记表示文件夹或文件驻留在Data Workbench服务器计算机上。
* A red check mark in the [!DNL Temp] column indicates that the local copy of the file or folder has the same Modified date and time as the file or folder on the Data Workbench server computer.
* A white check mark in the [!DNL Temp] column indicates that the file or folder in the *Data Workbench installation directory*\Temp directory has a different Modified date and time than the file or folder on the Data Workbench server computer.

The following graphic shows the [!DNL Server Files Manager] with both red and white check marks:

![](assets/vis_FileManager_RedWhiteChecks.png)

**使用[!DNL Server Files Manager]**

You can use the [!DNL Server Files Manager] to manipulate directories and files on a Data Workbench server computer.

The following table lists the tasks that can be completed using the [!DNL Server Files Manager]:

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
     <li id="li_3FDECC14D62543B183C3509C338DF432">路径。目录的路径。 </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">目录。目录的名称。 </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">来源。目录的位置，“远程”还是“临时”。 </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">日期（仅“临时”列）。本地副本的创建日期或上一次修订日期。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看有关文件的详细信息 </p> </td> 
   <td colname="col2"> <p>右键单击文件旁边服务器名称或“<span class="wintitle">临时</span>”列中的复选标记。会看到以下信息： </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">路径。文件的路径。 </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">文件。文件的名称 </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">来源。目录的位置，“远程”还是“临时”。 </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">页面. 文件上一次修订的日期。 </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">大小。文件的大小。 </li> 
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
   <td colname="col2"> <p>Right-click the check mark for the file in the <span class="wintitle"> Temp</span> column, click <span class="uicontrol"> Open</span>, then click in <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> in Notepad</span>, or <span class="uicontrol"> folder</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将目录的本地副本保存到Data Workbench Server </p> </td> 
   <td colname="col2"> <p>右键单击“<span class="wintitle">临时</span>”列中目录的复选标记，然后单击<span class="uicontrol">保存目录到</span> &gt; <i>&lt;<span class="uicontrol">配置文件名称</span>&gt;</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将文件的本地副本保存到Data Workbench Server </p> </td> 
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

