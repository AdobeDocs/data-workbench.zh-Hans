---
description: 将报表门户映射到虚拟目录（IIS 7.0或更高版本）的步骤。
title: 将报表门户映射到虚拟目录（IIS 7.0 或更高版本）
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 5%

---

# 将报表门户映射到虚拟目录（IIS 7.0 或更高版本）{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

{{eol}}

将报表门户映射到虚拟目录（IIS 7.0或更高版本）的步骤。

目前，大多数托管服务客户端都有服务器，其中带有Windows Server 2008操作系统和IIS 7.0或更高版本的Web服务器。

## 前提条件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* 确保ASP和 [!DNL ASP.Net] 组件安装的是IIS 7.0或更高版本。
* 确保IIS Web用户已 [!DNL Modify] 对 [!DNL E:\Portal\data\users.mdb] 文件。 您可以通过右键单击 **[!UICONTROL users.mdb]** 文件和下 [!DNL Properties]，转到 [!DNL Security] 选项卡。 如果未列出IIS Web用户，或者无法将IIS Web用户添加到列表，只需将 [!DNL Users] 组 [!DNL Modify] 访问权限。

* 确保使用任何用户帐户来运行 [!DNL Application Pools] 也有 [!DNL Modify] 对 [!DNL E:\Portal\data\users.mdb] 和[!DNL C:\Windows\Temp\]文件夹。

## 安装步骤 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. 在机器上， [!DNL Report Portal] ，启动 [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. 选择 **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. 右键单击 **[!UICONTROL Default Web Site]** 选择 **[!UICONTROL Add Virtual Directory]**.

1. 对于别名，请输入Portal。
1. 对于物理路径，输入 [!DNL E:\Portal\PortalASP].
1. 单击 **[!UICONTROL OK]**。

   您创建的虚拟目录显示在 [!DNL Default Web Site].

1. 在刚刚创建的虚拟目录下添加以下虚拟目录。

   | 创建此别名…… | 对于此物理资源 |
   |---|---|
   | 核心 | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 图像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 输出 | 目录的物理位置，其中 [!DNL Report Server] 保存报表集的输出。 输出文件夹可以位于任何位置，并可以命名为任何内容。 它包含每个报表集的子文件夹。 您可以删除 [!DNL E:\Portal\PortalFiles\Output]，但移动 [!DNL profiles.xml] 到输出文件的物理位置。 |

1. 完成后，验证IIS是否显示四个新的虚拟目录。 确保目录结构有一个父文件夹（与门户同名）和四个子文件夹。
1. 单击 **[!UICONTROL Application Pools]**，则 **[!UICONTROL DefaultAppPool]** （假设您使用门户设置了该门户）。

1. 单击 **[!UICONTROL Advanced Settings]** 并为“启用32位应用程序”选择“True”。
1. 要获取 [!DNL Portal] 要工作，您需要将其转换为应用程序。 设置虚拟目录后，右键单击Portal虚拟目录，然后选择 **[!UICONTROL Convert to Application]**.

## 其他提示和技巧 {#section-ff84ab3f66c94620a6a11f0e60471d44}

* 您可以下载 [!DNL Portal] 从 **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. 您只需下载 [!DNL ReportPortal-Release-1-0-0-7.zip].

* 您不再需要 [!DNL ReportPortalSetup.xml]，以便删除。
* 为了标准化，请将此zip文件的内容放入 [!DNL E:\Portal].
* 要确定托管服务客户端的SMTP服务器，您可以查看此处。
* 通过NetOps提出请求，将报表服务器的IIS中的域名条目更改为更易记的条目，例如， [!DNL reports.clientname.insight.omniture.com]，以便您的整个门户URL为 [!DNL https://reports.clientname.insight.omniture.com/Portal]. 配置 [!DNL email.asa] 文件。
