---
description: 报表门户由一组应用程序服务器页(ASP)和支持文件组成。
title: 安装报表门户应用程序文件
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# 安装报表门户应用程序文件{#install-the-report-portal-application-files}

报表门户由一组应用程序服务器页(ASP)和支持文件组成。

要安装[!DNL Report Portal]，必须从您从Adobe收到的分发文件中解压这些文件，并将它们安装到运行Microsoft IIS的计算机上。

**安装应用程 [!DNL Report Portal] 序文件**

1. 如果尚未下载[!DNL Report Portal]的安装包（.zip文件），请从Adobe FTP站点下载。
1. 在运行IIS的计算机上，将安装包中的文件解压缩到任意位置。 此步骤将在VSVirtualPortalName文件夹中安装以下子文件夹和文件。

   | 文件夹或文件 | 描述 |
   |---|---|
   | [!DNL \data\users.mdb] | 包含授权[!DNL Report Portal]用户列表的数据库。 |
   | [!DNL \PortalASP\] | 包含组成[!DNL Report Portal]的ASP文件的文件夹。 |
   | [!DNL \PortalFiles\] | 包含五个子文件夹（核心、CSS、HTC、图像和输出）的文件夹，其中包含[!DNL Report Portal]使用的支持文件。 |
   | [!DNL ReportPortalSetup.xml] | 用于定义与[!DNL Report Portal]关联的虚拟目录的配置文件（仅与IIS 6.0一起使用）。 |

   该目录如下例所示：

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >目录的名称可能与示例中显示的名称不同。

1. 将VSVirtualPortalName（或其他名称）文件夹重命名为要用作[!DNL Report Portal]的根虚拟目录（以下称为&#x200B;*PortalName*）的文件夹。 有关虚拟目录的详细信息，请参阅下一节。
