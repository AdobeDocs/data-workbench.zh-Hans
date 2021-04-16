---
description: 安装后，由Adobe颁发的数字证书将充当使您能够运行报表服务器的密钥。
title: 重新验证数字证书
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 13%

---

# 重新验证数字证书{#re-validating-the-digital-certificate}

安装后，由Adobe颁发的数字证书将充当使您能够运行报表服务器的密钥。

**推荐频率：** 根据需要

要正常工作，数字证书必须是最新的。

要保持最新，您的数字证书必须定期重新验证(通常为每30天重新验证一次，但这可能因您与Adobe的协议而异)。 如果您的计算机具有 Internet 访问权限，则重新验证过程将完全透明。[!DNL Report Server] 自动连接到Adobe License Server，并在必要时重新验证证书。如果您的计算机没有Internet访问权限，则必须从Adobe许可证服务器下载新的、经过验证的证书，并使用[下载和安装数字证书](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)中提供的步骤将其安装到您的计算机上。
