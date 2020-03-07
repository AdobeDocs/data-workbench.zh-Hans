---
description: 本快速指南提供了验证内部和外部FTP设置所需的最少步骤。
title: 内部和外部FTP服务器的验证
uuid: bc381c1d-df27-4009-920b-1a804b36c204
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# 内部和外部FTP服务器的验证{#validation-of-internal-and-external-ftp-servers}

本快速指南提供了验证内部和外部FTP设置所需的最少步骤。

当Adobe内部的顾问／架构师必须连接到FTP站点才能上传或下载文件时，会使用内部FTP，而外部FTP则主要供您作为上传所需数据文件的用户使用。

有关设置FTP服务器的其他信息，请参阅文 [件传输协议](https://docs.adobe.com/content/help/en/analytics/export/ftp-and-sftp/ftp-overview.html)。

## 验证步骤——外部FTP {#section-24428111b5c542ce81a765cd63424b97}

1. 打开命令提示符。 （Windows+R并键入cmd）
1. Type ftp `<ftp server>`
1. 提供用户名和密码。 ![](assets/dwb_impl_ftp1.png)

1. 更改可从中移动某些文件的本地目录。 使用以下命令：

[!DNL ftp> lcd C:\Users\andixit\Desktop]

本地目录 [!DNL C:\Users\andixit\Desktop]。

1. 将文件从本地复制到远程位置。 ![](assets/dwb_impl_ftp2.png)

1. 注销远程服务器。 （使用下面的命令）

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>验证FTP的另一种方法是使用Filezilla。 提供主机名、用户名、口令和端口。 面板的右侧是远程站点，左侧是本地站点。 验证FTP将文件从本地拖放到远程站点和v.v。

![](assets/dwb_impl_ftp3.png)

## 验证步骤——内部FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

可以按照上述步骤验证来自任何Adobe服务器的内部FTP。
