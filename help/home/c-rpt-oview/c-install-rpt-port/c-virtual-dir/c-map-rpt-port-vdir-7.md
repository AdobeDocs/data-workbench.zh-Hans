---
description: 将报表门户映射到虚拟目录（IIS 7.0或更高版本）的步骤。
title: 将报表门户映射到虚拟目录（IIS 7.0 或更高版本）
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# 将报表门户映射到虚拟目录（IIS 7.0 或更高版本）{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

将报表门户映射到虚拟目录（IIS 7.0或更高版本）的步骤。

目前，大多数托管服务客户端都有服务器，其中带有Windows Server 2008操作系统和IIS 7.0或更高版本的Web服务器。

## 先决条件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* 确保为IIS 7.0或更高版本安装ASP和[!DNL ASP.Net]组件。
* 确保IIS Web用户具有[!DNL Modify]对[!DNL E:\Portal\data\users.mdb]文件的访问权限。 可以通过右键单击&#x200B;**[!UICONTROL users.mdb]**&#x200B;文件并在[!DNL Properties]下方，转到[!DNL Security]选项卡。 如果未列出IIS Web用户，或者无法将IIS Web用户添加到列表，则只需为[!DNL Users]组授予[!DNL Modify]访问权限。

* 请确保任何用于运行[!DNL Application Pools]的用户帐户也具有[!DNL Modify]对[!DNL E:\Portal\data\users.mdb]和 [!DNL C:\Windows\Temp\] 文件夹的访问权限。

## 安装步骤 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. 在安装[!DNL Report Portal]的计算机上，启动[!DNL IIS Manager]:

   **[!UICONTROL Start]** >  **[!UICONTROL Administrative Tools]** >  **[!UICONTROL Internet Information Services (IIS) Manager]**。

1. 选择&#x200B;**[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**。

1. 右键单击&#x200B;**[!UICONTROL Default Web Site]**&#x200B;并选择&#x200B;**[!UICONTROL Add Virtual Directory]**。

1. 对于别名，请输入Portal。
1. 对于物理路径，输入[!DNL E:\Portal\PortalASP]。
1. 单击 **[!UICONTROL OK]**。

   您创建的虚拟目录显示在[!DNL Default Web Site]下。

1. 在刚刚创建的虚拟目录下添加以下虚拟目录。

   | 创建此别名…… | 对于此物理资源 |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 图像 | [!DNL E:\Portal\PortalFiles\Images] |
   | Output（输出） | [!DNL Report Server]保存报表集输出的目录的物理位置。 输出文件夹可以位于任何位置，并可以命名为任何内容。 它包含每个报表集的子文件夹。 您可以删除[!DNL E:\Portal\PortalFiles\Output]，但将[!DNL profiles.xml]移动到输出文件的物理位置。 |

1. 完成后，验证IIS是否显示四个新的虚拟目录。 确保目录结构有一个父文件夹（与门户同名）和四个子文件夹。
1. 单击&#x200B;**[!UICONTROL Application Pools]**，然后单击&#x200B;**[!UICONTROL DefaultAppPool]**（假设您使用门户设置了该页面）。

1. 单击&#x200B;**[!UICONTROL Advanced Settings]**，然后为“启用32位应用程序”选择“True”。
1. 要使[!DNL Portal]正常工作，您需要将其转换为应用程序。 设置虚拟目录后，右键单击Portal虚拟目录，然后选择&#x200B;**[!UICONTROL Convert to Application]**。

## 其他提示和技巧 {#section-ff84ab3f66c94620a6a11f0e60471d44}

* 您可以从&#x200B;**[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**&#x200B;下的Softdocs下载[!DNL Portal]。 您只需下载[!DNL ReportPortal-Release-1-0-0-7.zip]即可。

* 您不再需要[!DNL ReportPortalSetup.xml]，因此可以删除它。
* 为了标准化，请将此zip文件的内容放入[!DNL E:\Portal]中。
* 要确定托管服务客户端的SMTP服务器，您可以查看此处。
* 通过NetOps提出请求，将报表服务器的IIS中的域名条目更改为更易记的条目，例如[!DNL reports.clientname.insight.omniture.com]，这样您的整个门户URL就是[!DNL https://reports.clientname.insight.omniture.com/Portal]。 完成此更改后，配置[!DNL email.asa]文件。
