---
description: 安装后，由Adobe颁发的数字证书将用作用于运行报表服务器的密钥。
title: 重新验证数字证书（概述）
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 10%

---

# 重新验证数字证书{#re-validating-the-digital-certificate}

{{eol}}

安装后，由Adobe颁发的数字证书将用作用于运行报表服务器的密钥。

**推荐频率：** 根据需要

要正常运行，数字证书必须是最新的。

要保持最新，必须定期(通常每30天，但具体情况可能因您与Adobe的协议而异)重新验证您的数字证书。 如果您的计算机具有 Internet 访问权限，则重新验证过程将完全透明。[!DNL Report Server] 自动连接到Adobe许可证服务器，并在必要时重新验证证书。 如果您的计算机没有Internet访问权限，则必须从Adobe许可证服务器下载经过验证的新证书，然后按照 [下载并安装数字证书](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
