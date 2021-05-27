---
description: 打开功能使您可以在此外部程序（如文本编辑器或 Web 浏览器）中打开文档或 URI 等项目。
title: 配置打开功能
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 46%

---

# 配置打开功能{#configure-open-functionality}

打开功能使您可以在此外部程序（如文本编辑器或 Web 浏览器）中打开文档或 URI 等项目。

打开功能目前只能在 [!DNL Site] 应用程序中进行配置，并且仅用于打开 URI。本节提供了有关为 [!DNL Site] 配置“打开 URI”功能的信息。有关为其他应用程序配置打开功能或将该功能配置为打开其他项目的信息，请联系 Adobe 咨询服务部门。

在 [!DNL Site] 中，您可以从页面叠加或表格中右键单击 URI，以在设置 URI 格式的应用程序中显示此 URI。例如，从 URI 表格可视化中，您可以单击 URI 以在 Web 浏览器中显示网页。

要从可视化中打开URI，您必须首先编辑URI维度的[!DNL Open URI.cfg]文件，以标识Data Workbench用于打开URI的位置和命名约定。 要以本机格式（如HTML）查看URI，Data Workbench必须有权访问引用位置以及打开该项目所需的应用程序。 例如，要查看网页，Data Workbench既需要访问Internet，又需要安装Web浏览器。

**编辑 Open URI.vw**

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**。
1. 在URI文件夹中，右键单击[!DNL Open URI.vw]文件旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。
1. 右键单击新创建的复选标记，如果文件是[!DNL .cfg]文件，则单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**；如果文件是[!DNL .vw]文件，则单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
1. 单击&#x200B;**[!UICONTROL Command]**，然后单击&#x200B;**[!UICONTROL Parameters]**&#x200B;以查看文件的内容。
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
   <td colname="col2"> <p>Data Workbench应用于查找和打开URI的参数。 </p> <p>示例：<span class="filepath">http://%Site%%URI%</span>。 </p> <p>示例中显示的默认模板告知Data Workbench打开Web浏览器，查找在<span class="wintitle"> Site</span>参数中定义的位置，然后找到您尝试打开的URI维度元素。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 保存文件。
1. 若要使此更改对工作配置文件的所有用户可用，请右键单击[!DNL User]列中[!DNL .vw]文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL working profile name]**。
