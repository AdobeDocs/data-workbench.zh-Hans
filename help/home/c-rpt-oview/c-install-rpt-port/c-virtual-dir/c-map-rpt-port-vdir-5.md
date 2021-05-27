---
description: 将报表门户映射到虚拟目录(IIS 5.0)的步骤。
title: 将报表门户映射到虚拟目录 (IIS 5.0)
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# 将报表门户映射到虚拟目录 (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

将报表门户映射到虚拟目录(IIS 5.0)的步骤。

1. 在安装[!DNL Report Portal]的计算机上，使用&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**&#x200B;或&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**&#x200B;启动IIS管理器。

1. 选择&#x200B;**[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**。

1. 右键单击&#x200B;**[!UICONTROL Default Web Site]**&#x200B;并选择&#x200B;**[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 打开[!DNL Virtual Directory Wizard]时，单击&#x200B;**[!UICONTROL Next]**。

1. 完成以下步骤以定义[!DNL Report Portal]的根虚拟目录：

   1. 提示输入别名时，键入[!DNL Report Portal]的名称，然后单击&#x200B;**[!UICONTROL Next]**。 例如，如果要使用“Portal”作为[!DNL Report Portal]的名称，请将别名“Portal”分配给虚拟目录。 完成后单击 **[!UICONTROL Next]**。

   1. 提示输入物理路径时，浏览并选择&#x200B;*&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]**&#x200B;目录，然后单击&#x200B;**[!UICONTROL Next]**。

      示例：[!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. 提示输入权限时，请确认已启用以下选项：

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. 单击 **[!UICONTROL Next]**，然后单击 **[!UICONTROL Finish]**。您创建的虚拟目录将显示在默认网站下方，如以下示例所示。

   ![](assets/RptPort_scrn_VirDirManual.png)

1. 右键单击刚刚创建的虚拟目录，然后选择&#x200B;**[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 使用[!DNL Virtual Directory]向导为以下每个物理目录创建别名。 这样做会为每个这些物理资源创建一个名称正确的虚拟目录。

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 创建此别名。.. </th> 
   <th colname="col2" class="entry"> 对于此物理资源。.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Core </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>示例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>示例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>示例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 图像 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>示例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output（输出） </td> 
   <td colname="col2"> <p><span class="keyword">报表服务器</span>保存报表集输出的目录的物理位置。 输出文件夹可以位于任意位置，可以命名为任何内容，并包含每个报表集的子文件夹。 </p> <p>此目录必须与您在报表集<span class="filepath"> Report.cfg</span>文件的Output Root参数中指定的目录相同。 有关更多信息，请参阅<a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d">配置Report.cfg文件</a>。 </p> <p>默认位置为\<i>PortalName</i>\PortalFiles\Output。 </p> <p>示例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p><i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> profiles.xml</span>文件，必须将其移至您为此别名指定的输出目录。 </p> <p>正确设置<span class="wintitle">路径</span>属性至关重要。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 完成后，验证IIS是否显示六个新的虚拟目录。 确保目录结构有一个父文件夹（与门户的名称相同）和五个子文件夹，如下所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 完成后，转到[编辑会话配置文件](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)以继续安装过程。
