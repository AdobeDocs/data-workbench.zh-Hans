---
description: 安装后，Adobe颁发的数字证书将用作允许您运行Report Server的密钥。
solution: Analytics
title: 重新验证数字证书
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 重新验证数字证书{#re-validating-the-digital-certificate}

安装后，Adobe颁发的数字证书将用作允许您运行Report Server的密钥。

**推荐频率：** 根据需要

要正常工作，数字证书必须是最新的。

要保持最新，您的数字证书必须定期（通常每30天重新验证一次，但这可能因您与Adobe的协议而异）。 如果您的计算机可以访问Internet，则重新验证过程完全透明。 [!DNL Report Server] 自动连接到Adobe License Server，并在必要时重新验证证书。 如果您的计算机无法访问Internet，则必须从Adobe许可证服务器下载经过验证的新证书，并按照下载和安装数字证书中提供的步骤将其安装到您的 [计算机上](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)。
