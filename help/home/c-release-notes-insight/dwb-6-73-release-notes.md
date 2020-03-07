---
description: Data Workbench 6.73中的新增功能和修复。
title: Data Workbench 6.73 发行说明
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.73 发行说明{#data-workbench-release-notes}

Data Workbench 6.73中的新增功能和修复。

## Data Workbench 6.73 发行说明 {#topic-7655534554ac4a4b816af1bd73b06aad56757}

Data Workbench 6.73中的新增功能和修复。

## 修复 {#section-160baf6ea04c45a993777ee4260691ed}

* 修复了工作站存在的一个问题：用户无法登录某些使用高分辨率和高 DPI 的硬件。
* 修复了服务器中使用IMS登录时，“存档”文件名中缺少电子邮件的问题。
* 已将 OpenSSL 更新到版本 1.1.0h， 此版本修复了多个漏洞，并提供了新的 SSL 密码。
* 将下面列出的开放源库更新为最新的稳定版本

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* 添加了当查询文件行数超过支持的 357913908 行时记录错误日志的功能。

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench Workstation版本6.73不连接到Data Workbench Servers版本6.61及更早版本。 原因是，旧版服务器使用版本6.73中不支持的弱密码形式。启用对旧版本的支持

   1. 使用OpenSSL版本1.0.1h支持的强密码列表覆盖服务器上的默认SSL密码列表。 要覆盖，请在“组件”和“处理服务器组件”目录中提供的“Communications.cfg”文件中添加密钥“SSL密码”。 例如：`SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >确保将密钥放在与SSL端口相同的级别。 有关详细信息，请参阅 [通信配置设置](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. 将最新的trust_ca_cert.pem文件放在服务器6.61及更早的服务器上。 此设置适用于所有Workstation 6.7x版本。

请参阅 Data Workbench 5.3 至 5.52 的[已存档发行说明](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)。
