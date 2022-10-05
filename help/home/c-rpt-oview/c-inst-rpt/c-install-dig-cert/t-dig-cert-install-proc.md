---
description: 下载并安装数字证书的步骤。
title: 数字证书的安装步骤
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 42%

---

# 数字证书的安装步骤{#digital-certificate-installation-procedures}

{{eol}}

下载并安装数字证书的步骤。

1. 打开 Web 浏览器，以访问 [https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >此时，您的浏览器可能会提示您提供数字证书。如果是，只需单击 **[!UICONTROL Cancel]** 关闭对话框。

1. 在登录屏幕上，输入您从Adobe收到的帐户名称和密码，然后单击 **[!UICONTROL login]**.
1. 找到为实例颁发的证书 [!DNL Report] 服务器(*您的姓名*.pem)，然后单击 ![](assets/btn_save_certificatedownload.PNG) 与该证书关联的图标。
1. 提示保存证书时，单击 **[!UICONTROL Save]**。
1. 将文件下载到 安装目录中的 [!DNL Report Server]Certificates 文件夹中。

   此文件夹已包含一个名为 [!DNL trust_ca_cert.pem] 的证书文件。两个证书文件必须始终存在 [!DNL Report] 服务器。
