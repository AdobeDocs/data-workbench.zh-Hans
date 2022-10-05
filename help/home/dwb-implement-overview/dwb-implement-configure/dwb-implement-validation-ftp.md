---
description: 本快速指南提供了验证内部和外部FTP设置所需的最低步骤。
title: 验证内部和外部 FTP 服务器
uuid: bc381c1d-df27-4009-920b-1a804b36c204
exl-id: 8eecfda7-ffa0-458c-a518-434758344bfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# 验证内部和外部 FTP 服务器{#validation-of-internal-and-external-ftp-servers}

{{eol}}

本快速指南提供了验证内部和外部FTP设置所需的最低步骤。

当Adobe的内部顾问/架构师必须连接到FTP站点才能上传或下载文件时，会使用内部FTP，而外部FTP主要供用户上传所需的数据文件。

有关设置FTP服务器的其他信息，请参阅 [文件传输协议](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html?lang=zh-Hans).

## 验证步骤 — 外部FTP {#section-24428111b5c542ce81a765cd63424b97}

1. 打开命令提示符。 （Windows+R并键入cmd）
1. 类型ftp `<ftp server>`
1. 提供用户名和密码。 ![](assets/dwb_impl_ftp1.png)

1. 更改可从中移动某些文件的本地目录。 使用以下命令：

[!DNL ftp> lcd C:\Users\andixit\Desktop]

立即本地目录 [!DNL C:\Users\andixit\Desktop].

1. 将文件从本地复制到远程位置。 ![](assets/dwb_impl_ftp2.png)

1. 从远程服务器注销。 （使用下面的命令）

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>验证FTP的另一种方法是使用Filezilla。 提供主机名、用户名、密码和端口。 面板的右侧是远程站点，左侧是本地站点。 验证FTP将文件从本地拖放到远程站点和v.v。

![](assets/dwb_impl_ftp3.png)

## 验证步骤 — 内部FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

可以按照上述步骤验证来自任何Adobe服务器的内部FTP。
