---
description: 有关设置查询API的快速指南。
title: 查询 API 设置
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
exl-id: 8b9dace8-4dad-434c-aec3-2f6ca872a5f6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---

# 查询 API 设置{#query-api-setup}

{{eol}}

有关设置查询API的快速指南。

请按照以下步骤设置查询API:

1. 查询API证书客户获取

   向技术运营团队发送电子邮件Adobe- `Dataworkbench@adobe.com`.

   请提供要用于查询API的CN名称(提供类似 `<Client>` 查询API)。

   >[!NOTE]
   >
   >技术运营人员将生成证书并将其上传到URL中。 在成功生成票证时收到技术运营部门的通知后，请告知Adobe顾问，以便票证将由他们发送回您。

1. 下载和提取API特效。 从您的顾问处获取api特定程序文件。

   确保在计算机上安装了Perl。

   在提取的文件夹（复制文件的文件夹路径）中，将查询API证书复制到 *特技* 文件夹。

1. 配置Stunnel.conf

   应该有一个名为 *stunnel.conf* 内部 *斯图内尔* 文件夹（您复制证书的位置）。

   在记事本中编辑文件。

   ![](assets/dwb_impl_API1.png)

   按如下方式更改参数： ![](assets/dwb_impl_API2.png)

   此文件中需要更改两个参数。

   * *证书* =证书上的名称。 在此示例中为Aadhithiya Ramani QAPI Client.pem。
   * *连接* =主DPU的服务器名称。

1. 复制 *Query.pm*.

   的 *Query.pm* 文件将在Insight API文件夹中可用。

   复制 *Query.pm* 文件并将其粘贴到Perl库文件夹中(通常为*C:\Perl64\lib *，但检查Perl在计算机中的安装位置)。

1. 修改 *api-http.pl* 文件

   api-http.pl文件将在api-stunnel文件夹中可用。

   只有一个要修改的参数

   *我的$个人资料* =要为其配置查询API的配置文件名称。

1. 安装查询API。

   以“管理员”身份在系统中打开命令提示符，然后导航到解压的目录 *特技* 如下所示： ![](assets/dwb_impl_API3.png)

   运行以下命令 *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   执行命令后，将弹出一个窗口，指示 *特技* 已安装。

   >[!NOTE]
   >
   >执行命令后，将弹出一个窗口，指示 *特技* 已安装。

1. 测试查询API失效配置

   此过程的最后一步是测试查询API配置。 在用于安装api-stunnel目录的命令提示符下。 ![](assets/dwb_impl_API5.png)

   使用以下命令* perl api-http.pl*运行该文件夹中可用的Perl脚本。 ![](assets/dwb_impl_API6.png)

   运行脚本后，结果应类似于下面的屏幕截图（在步骤6中）（截止时间和结果中的值，将根据您在其上配置了查询API的配置文件中的其他参数而有所不同）。 ![](assets/dwb_impl_API7.png)
