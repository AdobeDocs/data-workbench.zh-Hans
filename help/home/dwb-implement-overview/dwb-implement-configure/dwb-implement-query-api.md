---
description: 设置查询API的快速指南。
title: 查询API设置
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查询API设置{#query-api-setup}

设置查询API的快速指南。

请按照以下步骤设置Query API:

1. 查询API证书获取

   向Adobe Tech Ops团队发送电子邮件- `Dataworkbench@adobe.com`

   请提供要用于查询API的CN名称(提供一个通用名称，如 `<Client>` Query API)。

   >[!NOTE]
   >
   >Tech Ops将生成证书并将其上传到URL中。 在成功生成票证时，请在收到技术运营部门的通知后通知Adobe顾问，以便他们将票证发回给您。

1. 下载和提取API Stunnel。 从您的顾问处获得apistunnel文件。

   确保Perl已安装在您的计算机上。

   在提取的文件夹（复制文件的文件夹路径）中，将您的Query API证书复制到stunnel文 *件夹* 。

1. 配置Stunnel.conf

   Stunnel文件夹中应有一 *个名为stunnel.conf* ( ** 您复制证书的位置)。

   在记事本中编辑文件。

   ![](assets/dwb_impl_API1.png)

   按如下方式更改参数： ![](assets/dwb_impl_API2.png)

   此文件中需要更改两个参数。

   * *Cert* =证书上的名称。 在此示例中，它是Aadhithiya Ramani QAPI Client.pem。
   * *Connect* =主DPU的服务器名称。

1. 复制 *Query.pm*。

   *Query.pm* 文件将位于Insight API文件夹中。

   复制 *Query.pm* 文件并将其粘贴到Perl库文件夹中(通常为*C:\Perl64\lib *，但检查Perl在计算机中的安装位置)。

1. 修改 *api-http.pl文件*

   api-http.pl文件将位于api-stunnel文件夹中。

   仅一个要修改的参数

   *我的$profile* =要为其配置Query API的配置文件名称。

1. 安装Query API。

   在系统中以“Administrator”的身份打开命令提示符，然后导航到解压stunnel的目 *录* ，如下所示： ![](assets/dwb_impl_API3.png)

   Run the following command *.\stunnel -install*。 ![](assets/dwb_impl_API4.png)

   执行命令后，窗口将弹出，表示已安装 *stunnel* 。

   >[!NOTE]
   >
   >执行命令后，窗口将弹出，表示已安装 *stunnel* 。

1. 测试Query API的stunnel配置

   此过程的最后一步是测试Query API配置。 在用于安装api-stunnel目录的命令提示符下。 ![](assets/dwb_impl_API5.png)

   使用以下命令* perl api-http.pl*运行该文件夹中可用的Perl脚本。 ![](assets/dwb_impl_API6.png)

   运行脚本后，结果应类似于下面的屏幕截图（在步骤6中）（截止时间和结果中的值将因您配置Query API的配置文件中的其他参数而异）。 ![](assets/dwb_impl_API7.png)

