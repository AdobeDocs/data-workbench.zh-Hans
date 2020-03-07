---
description: 下载并安装数字证书的步骤。
solution: Analytics
title: 数字证书安装过程
topic: Data workbench
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 数字证书安装过程{#digital-certificate-installation-procedures}

下载并安装数字证书的步骤。

1. 打开Web浏览器至 [https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >此时，您的浏览器可能会提示您提供数字证书。 If it does, just click **[!UICONTROL Cancel]** to dismiss the dialog box.

1. On the login screen, enter the Account Name and the Password that you received from Adobe, then click **[!UICONTROL login]**.
1. Locate the certificate that has been issued for your instance of [!DNL Report] Server (*Your Name*.pem) and click the ![](assets/btn_save_certificatedownload.PNG) icon associated with that certificate.
1. When prompted to save the certificate, click **[!UICONTROL Save]**.
1. 将文件下载到 安装目录中的 [!DNL Report Server]Certificates 文件夹中。

   This folder already contains a certificate file named [!DNL trust_ca_cert.pem]. Both certificate files must always be present for [!DNL Report] Server to function.

