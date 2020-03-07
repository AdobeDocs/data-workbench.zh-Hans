---
description: 将Report Portal映射到虚拟目录（IIS 7.0或更高版本）的步骤。
solution: Analytics
title: 将报告门户映射到虚拟目录（IIS 7.0或更高版本）
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 将报告门户映射到虚拟目录（IIS 7.0或更高版本）{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

将Report Portal映射到虚拟目录（IIS 7.0或更高版本）的步骤。

目前，大多数Managed Service客户端都有服务器，服务器装有Windows Server 2008操作系统和IIS 7.0或更高版本的Web服务器。

## 先决条件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* 确保IIS 7.0或 [!DNL ASP.Net] 更高版本安装了ASP和组件。
* 确保IIS Web用户有权 [!DNL Modify] 访问该文 [!DNL E:\Portal\data\users.mdb] 件。 您可以通过右键单击文件来更改该 **[!UICONTROL users.mdb]** 设置，然后 [!DNL Properties]转到选项卡 [!DNL Security] 下。 如果未列出IIS Web用户，或者无法将IIS Web用户添加到列表，只需向组授予访 [!DNL Users] 问权 [!DNL Modify] 限。

* 确保使用任何用户帐户运行文件 [!DNL Application Pools] 夹，也 [!DNL Modify] 有权访问 [!DNL E:\Portal\data\users.mdb] 和[!DNL C:\Windows\Temp\]文件夹。

## 安装步骤 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. 在安装了以 [!DNL Report Portal] 下代码的计算机上，启动 [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. 选择 **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. 右键单击 **[!UICONTROL Default Web Site]** 并选择 **[!UICONTROL Add Virtual Directory]**。

1. 对于别名，请输入门户。
1. 对于物理路径，输入 [!DNL E:\Portal\PortalASP]。
1. 单击 **[!UICONTROL OK]**.

   您创建的虚拟目录显示在 [!DNL Default Web Site]下。

1. 在刚刚创建的虚拟目录下添加以下虚拟目录。

   | 创建此别名…… | 对于此物理资源 |
   |---|---|
   | 核心 | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 图像 | [!DNL E:\Portal\PortalFiles\Images] |
   | Output（输出） | 保存报表集输出的目 [!DNL Report Server] 录的物理位置。 输出文件夹可以位于任何位置，并且可以命名为任何内容。 它包含每个报告集的子文件夹。 您可以删除该 [!DNL E:\Portal\PortalFiles\Output]文件，但将其移 [!DNL profiles.xml] 到输出文件的物理位置。 |

1. 完成后，验证IIS显示四个新的虚拟目录。 确保目录结构有一个父文件夹（与门户名称相同）和四个子文件夹。
1. 单击， **[!UICONTROL Application Pools]**&#x200B;然后(假 **[!UICONTROL DefaultAppPool]** 定您使用门户设置了该选项)。

1. 单击并 **[!UICONTROL Advanced Settings]** 为“启用32位应用程序”选择“真”。
1. 要使工 [!DNL Portal] 作正常，您需要将其转换为应用程序。 设置虚拟目录后，右键单击门户虚拟目录并选择 **[!UICONTROL Convert to Application]**。

## 其他提示与技巧 {#section-ff84ab3f66c94620a6a11f0e60471d44}

* 您可以从>下 [!DNL Portal] 的Softdocs下载 **[!UICONTROL Softdocs]** 该文 **[!UICONTROL Report Portal]**&#x200B;件。 您只需下载 [!DNL ReportPortal-Release-1-0-0-7.zip]。

* 您不再需要 [!DNL ReportPortalSetup.xml]，因此可以删除它。
* 为了标准化，请将此zip文件的内容放入其中 [!DNL E:\Portal]。
* 要确定SMTP服务器对于托管服务客户端，您可以在此处查看。
* 在NetOps中输入请求，将报表服务器的IIS中的域名条目更改为更友好的条目，例如， [!DNL reports.clientname.insight.omniture.com]，这样您的整个门户URL就是 [!DNL http://reports.clientname.insight.omniture.com/Portal]。 完成 [!DNL email.asa] 此更改后，配置文件。

