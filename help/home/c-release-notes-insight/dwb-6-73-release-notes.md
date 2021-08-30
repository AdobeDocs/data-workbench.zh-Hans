---
description: Data Workbench6.73的新增功能和修复。
title: Data Workbench 6.73 发行说明
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 30%

---

# Data Workbench 6.73 发行说明{#data-workbench-release-notes}

Data Workbench6.73的新增功能和修复。

## 修复 {#section-160baf6ea04c45a993777ee4260691ed}

* 修复了工作站存在的一个问题：用户无法登录某些使用高分辨率和高 DPI 的硬件。
* 修复了使用IMS登录时，存档文件名中缺少电子邮件的服务器问题。
* 已将 OpenSSL 更新到版本 1.1.0h， 此版本修复了多个漏洞，并提供了新的 SSL 密码。
* 已将下面列出的开源库更新到最新的稳定版本

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* 添加了当查询文件行数超过支持的 357913908 行时记录错误日志的功能。

## 已知问题 {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench工作站版本6.73未连接到Data Workbench服务器版本6.61及更低版本。 原因是，旧版服务器使用的密码形式较弱，在版本6.73中不受支持。要启用对旧版本的支持

   1. 使用OpenSSL版本1.0.1h支持的强密码列表覆盖服务器上的默认SSL密码列表。 要覆盖，请在“组件”和“处理服务器的组件”目录中提供的“Communications.cfg”文件中添加密钥“SSL密码”。 例如：`SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >确保将密钥放置在与SSL端口相同的级别。 有关详细信息，请参阅[通信配置设置](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. 将最新的trust_ca_cert.pem文件放在服务器6.61及更旧的服务器上。 此设置适用于所有工作站6.7x版本。

请参阅 Data Workbench 5.3 至 5.52 的[已存档发行说明](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html)。
