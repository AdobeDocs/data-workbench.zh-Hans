---
description: 要使用报表门户，必须在IIS上安装和配置一组应用程序服务器页面(ASP)。
title: 安装报表门户
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 11%

---

# 安装报表门户{#installing-the-report-portal}

{{eol}}

要使用报表门户，必须在IIS上安装和配置一组应用程序服务器页面(ASP)。

**开始之前**

本章中的步骤介绍了如何安装和配置 [!DNL Report Portal]. 要完成这些步骤，您必须：

* 已安装Microsoft IIS并了解其版本。
* 知道其报表显示方式的报表集的名称 [!DNL Report Portal].
* 了解目录的位置，其中 [!DNL Report Server] 保存这些报表集的输出。 确保IIS应用程序服务器具有此目录的访问权限。

>[!NOTE]
>
>* 要使用 [!DNL Report Portal]，则报表必须遵循特定的命名约定。 此外，保存报告的目录必须遵循规定的结构。 有关这些要求的描述，请参阅 [确保您的报表集与报表门户兼容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
>
>* 报表门户中的密码现在符合AES-256位标准。 如果升级到Report Portal 2.0，请将 **users.mdb** 数据库。 需要增加字段大小，才能使用更新的加密密码。
>* 如果要升级到Report Portal 2.0，请增加 **密码** users.mdb数据库中的字段50到150之间。 需要增加字段大小，才能使用更新的加密密码。
>* 现在，Report Portal 的哈希算法更加强大，并支持加盐。如果您要升级到 **报表门户2.1**，添加新文本字段， *PasswordSalt* 字段大小为20个字符 [!DNL users.mdb]数据库。 要存储密码盐，需要使用此字段。
>

