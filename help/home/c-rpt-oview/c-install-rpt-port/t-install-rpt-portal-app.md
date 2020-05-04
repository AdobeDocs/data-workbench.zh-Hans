---
description: 报表门户由一组应用程序服务器页面(ASP)和支持文件组成。
solution: Analytics
title: 安装Report Portal应用程序文件
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: 7521fe7f5fabe8e1be26e140ffff577a42fce88b

---


# 安装Report Portal应用程序文件{#install-the-report-portal-application-files}

报表门户由一组应用程序服务器页面(ASP)和支持文件组成。

要安装该 [!DNL Report Portal]文件，您必须从您从Adobe收到的分发文件中解压这些文件，并将它们安装在运行Microsoft IIS的计算机上。

**安装应用程[!DNL Report Portal]序文件**

1. 如果尚未这样做，请从Adobe FTP站点下载安装包( [!DNL Report Portal] .zip文件)。
1. 在运行IIS的计算机上，将安装包中的文件解压缩到任意位置。 此步骤将在VSVirtualPortalName文件夹中安装以下子文件夹和文件。

   | 文件夹或文件 | 描述 |
   |---|---|
   | [!DNL \data\users.mdb] | 包含授权用户列表的 [!DNL Report Portal] 数据库。 |
   | [!DNL \PortalASP\] | 包含构成ASP文件的文件夹 [!DNL Report Portal]。 |
   | [!DNL \PortalFiles\] | 包含五个子文件夹（核心、CSS、HTC、图像和输出）的文件夹，其中包含支持文件 [!DNL Report Portal]。 |
   | [!DNL ReportPortalSetup.xml] | 用于定义与关联的虚拟目录的配置 [!DNL Report Portal] 文件（仅与IIS 6.0一起使用）。 |

   该目录如下所示：

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >目录的名称可能与示例中显示的名称不同。

1. 将VSVirtualPortalName（或其他名称）文件夹重命名为要用作您的根虚拟目录 [!DNL Report Portal] (以下称为 *PortalName*)的文件夹。 有关虚拟目录的详细信息，请参阅下一节。
