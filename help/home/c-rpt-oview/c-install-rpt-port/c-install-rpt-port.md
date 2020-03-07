---
description: 要使用Report Portal，必须在IIS上安装和配置一组应用程序服务器页(ASP)。
solution: Analytics
title: 安装Report Portal
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装Report Portal{#installing-the-report-portal}

要使用Report Portal，必须在IIS上安装和配置一组应用程序服务器页(ASP)。

**开始之前**

本章中的步骤介绍了如何安装和配置 [!DNL Report Portal]。 要完成这些过程，您必须：

* 已安装Microsoft IIS并了解其版本。
* 了解报告集的名称，其报告由显示 [!DNL Report Portal]。
* 了解保存这些报告集输 [!DNL Report Server] 出的目录的位置。 确保IIS应用程序服务器有权访问此目录。

>[!NOTE]
>
>* 要使用查看报告， [!DNL Report Portal]必须遵循特定的命名惯例。 此外，保存报告的目录必须遵循指定的结构。 有关这些要求的说明，请参 [阅确保报表集与报表门户兼容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* 报告门户中的口令现在符合AES-256位规范。 如果升级到Report Portal 2.0，请将users.mdb数据库中的“密码字段大小”字段从50 **增加到150** 。 需要增加字段大小，才能容纳具有更新加密的密码。
>* 如果要升级到Report Portal 2.0，请将users.mdb数据库中“ **Password** ”字段的“字段大小”从50增加到150。 需要增加字段大小，才能容纳具有更新加密的密码。
>* 现在，Report Portal 的哈希算法更加强大，并支持加盐。If you are upgrading to **Report Portal 2.1**, add a new Text field, *PasswordSalt* with field size of 20 characters in [!DNL users.mdb]database. 要存储密码盐，需要使用此字段。
>



