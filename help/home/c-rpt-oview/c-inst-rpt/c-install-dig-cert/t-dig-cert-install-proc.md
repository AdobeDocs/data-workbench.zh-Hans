---
description: 下载并安装数字证书的步骤。
title: 数字证书的安装步骤
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 42%

---

# 数字证书的安装步骤{#digital-certificate-installation-procedures}

下载并安装数字证书的步骤。

1. 打开 Web 浏览器，以访问 [https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >此时，您的浏览器可能会提示您提供数字证书。如果是，则单击&#x200B;**[!UICONTROL Cancel]**&#x200B;关闭该对话框。

1. 在登录屏幕上，输入您从Adobe收到的帐户名和密码，然后单击&#x200B;**[!UICONTROL login]**。
1. 找到为[!DNL Report] Server（*您的名称*.pem）的实例颁发的证书，然后单击与该证书关联的![](assets/btn_save_certificatedownload.PNG)图标。
1. 提示保存证书时，单击 **[!UICONTROL Save]**。
1. 将文件下载到 安装目录中的 [!DNL Report Server]Certificates 文件夹中。

   此文件夹已包含一个名为 [!DNL trust_ca_cert.pem] 的证书文件。要使[!DNL Report]服务器正常运行，必须始终存在两个证书文件。
