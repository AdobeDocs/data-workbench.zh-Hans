---
description: 要使用Report Portal，必须在IIS上安装和配置一组应用程序服务器页(ASP)。
title: 安装报表门户
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 11%

---

# 安装报表门户{#installing-the-report-portal}

要使用Report Portal，必须在IIS上安装和配置一组应用程序服务器页(ASP)。

**开始之前**

本章中的步骤介绍如何安装和配置[!DNL Report Portal]。 要完成这些过程，您必须：

* 已安装Microsoft IIS并了解其版本。
* 了解报告集的名称，其报告由[!DNL Report Portal]显示。
* 了解[!DNL Report Server]保存这些报表集输出的目录位置。 确保IIS应用程序服务器有权访问此目录。

>[!NOTE]
>
>* 要使用[!DNL Report Portal]查看报告，必须遵循特定的命名约定。 此外，保存报表的目录必须遵循指定的结构。 有关这些要求的说明，请参阅[确保您的报表集与报表门户兼容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)。
   >
   >
* 报表门户中的密码现在符合AES-256位规范。 如果升级到Report Portal 2.0，请将&#x200B;**users.mdb**&#x200B;数据库中的“Field Size for Password”（口令字段大小）字段从50增加到150。 需要增加字段大小，以通过更新的加密来容纳密码。
>* 如果要升级到Report Portal 2.0，请将users.mdb数据库中&#x200B;**Password**&#x200B;字段的“字段大小”从50增加到150。 需要增加字段大小，以通过更新的加密来容纳密码。
>* 现在，Report Portal 的哈希算法更加强大，并支持加盐。如果要升级到&#x200B;**Report Portal 2.1**，请在[!DNL users.mdb]数据库中添加一个新的“文本”字段&#x200B;*PasswordSalt*，字段大小为20个字符。 要存储密码盐，需要使用此字段。

>


