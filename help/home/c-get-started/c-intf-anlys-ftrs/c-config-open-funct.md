---
description: 打开功能使您可以在此外部程序（如文本编辑器或 Web 浏览器）中打开文档或 URI 等项目。
solution: Analytics
title: 配置打开功能
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置打开功能{#configure-open-functionality}

打开功能使您可以在此外部程序（如文本编辑器或 Web 浏览器）中打开文档或 URI 等项目。

打开功能目前只能在 [!DNL Site] 应用程序中进行配置，并且仅用于打开 URI。本节提供了有关为 [!DNL Site] 配置“打开 URI”功能的信息。有关为其他应用程序配置打开功能或将该功能配置为打开其他项目的信息，请联系 Adobe 咨询服务部门。

在 [!DNL Site] 中，您可以从页面叠加或表格中右键单击 URI，以在设置 URI 格式的应用程序中显示此 URI。例如，从 URI 表格可视化中，您可以单击 URI 以在 Web 浏览器中显示网页。

To open a URI from a visualization, you first must edit the [!DNL Open URI.cfg] file for the URI dimension to identify the location and naming conventions that Data Workbench uses to open the URI. 要以本机格式（如HTML）查看URI,Data Workbench必须有权访问引用的位置以及打开该项目所需的应用程序。 例如，要查看网页，Data Workbench需要访问Internet并安装Web浏览器。

**编辑 Open URI.vw**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. In the URI folder, right-click the check mark next to the [!DNL Open URI.vw]file and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记， **[!UICONTROL Open]** 然后单 **[!UICONTROL in Insight]** 击 [!DNL .cfg] >（如果文件是文件）或 **[!UICONTROL Open]** >(如 **[!UICONTROL in Notepad]** 果是文件) [!DNL .vw] 。
1. Click **[!UICONTROL Command]**, then **[!UICONTROL Parameters]** to view the contents of the file.
1. 根据需要修改 [!DNL Site]（网站）参数和 Template（模板）参数：

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对于该参数... </th> 
   <th colname="col2" class="entry"> 提供此信息... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Site（网站） </p> </td> 
   <td colname="col2"> <p>您想要打开的 URI 的位置。 </p> <p>示例：mysite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>模板 </p> </td> 
   <td colname="col2"> <p>Data Workbench应用于查找和打开URI的参数。 </p> <p>示例：<span class="filepath">http://%Site%%URI%</span>。 </p> <p>The default template shown in the example tells Data Workbench to open a web browser, look for the location defined in the <span class="wintitle"> Site</span> parameter, then locate the URI dimension element you are attempting to open. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 保存文件。
1. To make this change available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

