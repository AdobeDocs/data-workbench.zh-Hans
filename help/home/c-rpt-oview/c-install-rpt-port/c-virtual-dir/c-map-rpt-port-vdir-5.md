---
description: 将Report Portal映射到虚拟目录(IIS 5.0)的步骤。
solution: Analytics
title: 将报告门户映射到虚拟目录(IIS 5.0)
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 将报告门户映射到虚拟目录(IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

将Report Portal映射到虚拟目录(IIS 5.0)的步骤。

1. 在安装计算机上，使用> > > [!DNL Report Portal] >或 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** >启动IIS Manager **[!UICONTROL Administrative Tools]****[!UICONTROL Internet Information Services]****[!UICONTROL Start]****[!UICONTROL Administrative Tools]****[!UICONTROL Internet Information Services]**。

1. 选择 **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 右键单击 **[!UICONTROL Default Web Site]** 并选择 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 打开时 [!DNL Virtual Directory Wizard] ，单击 **[!UICONTROL Next]**。

1. 完成以下步骤以为定义根虚拟目录 [!DNL Report Portal]:

   1. 当提示输入别名时，键入别名的名称 [!DNL Report Portal]，然后单击 **[!UICONTROL Next]**。 例如，如果要使用“门户”作为您的名称， [!DNL Report Portal]请将别名“门户”分配到虚拟目录。 完成后单击 **[!UICONTROL Next]**。

   1. 当提示输入物理路径时，浏览并选择&lt; *>**[!UICONTROL PortalName]*** Directory，然后单击 **[!UICONTROL \PortalASP]****[!UICONTROL Next]**。

      示例：[!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. 当提示您输入权限时，请验证是否启用了以下选项：

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Click **[!UICONTROL Next]**, then click **[!UICONTROL Finish]**. 您创建的虚拟目录显示在默认网站下方，如以下示例所示。
   ![](assets/RptPort_scrn_VirDirManual.png)

1. 右键单击刚创建的虚拟目录，然后选择 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**。

1. 使用向 [!DNL Virtual Directory] 导为以下每个物理目录创建别名。 这样做会为每个这些物理资源创建一个相应命名的虚拟目录。

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 创建此别名。.. </th> 
   <th colname="col2" class="entry"> 对于此物理资源。.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 核心 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>示例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>示例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>示例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 图像 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>示例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output（输出） </td> 
   <td colname="col2"> <p>Report Server保存报表集输出的 <span class="keyword"> 目录的物理位置</span> 。 输出文件夹可以位于任何位置，可以命名为任何内容，并包含每个报告集的子文件夹。 </p> <p>它必须与在Report.cfg文件中的Output Root参数中为报表集指定的 <span class="filepath"> 目录相同</span> 。 有关详细信息，请参 <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> 阅配置Report.cfg文件</a>。 </p> <p>默认位置为\<i>PortalName</i>\PortalFiles\Output。 </p> <p>示例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>PortalName <i></i>\PortalFiles\Output directory contains the <span class="filepath"></span> profiles.xml文件，必须将其移至您为此别名指定的输出目录。 </p> <p>正确设置“路径 <span class="wintitle"></span> ”属性至关重要。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 完成后，验证IIS是否显示六个新的虚拟目录。 确保目录结构有一个父文件夹（与门户名称相同）和五个子文件夹，如下所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 完成后，转到 [编辑会话配置文件](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) ，继续安装过程。

