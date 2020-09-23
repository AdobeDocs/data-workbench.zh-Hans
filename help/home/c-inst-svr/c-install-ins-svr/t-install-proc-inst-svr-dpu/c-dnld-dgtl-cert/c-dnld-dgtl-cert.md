---
description: 有关数字证书的一般信息以及下载和安装数字证书的过程。
solution: Analytics
title: 下载并安装数字证书
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 15%

---


# 下载并安装数字证书{#downloading-and-installing-the-digital-certificates}

有关数字证书的一般信息以及下载和安装数字证书的过程。

* [了解数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [节点锁定证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [最新证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [在无Internet访问的机器上使用数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [数字证书的安装过程](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## 了解数字证书 {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe 使用 X.509 数字证书标识和验证构成实施的客户端和服务器组件。

安装服务器组件(或 [!DNL Insight Server] ) [!DNL Repeater]时，必须安装Adobe为该组件颁发的数字证书。 如果您需要将Adobe应用程序迁移到另一台计算机，则必须从Adobe获取新证书。 为此，请与Adobe客户关怀联系。

此证书上显示的公用名称通过指定的域名(例如， [!DNL vs001a.mycompany.com])标识服务器。 当服务器客户端连接到此服务器时，服务器将此证书显示为验证，事实上它是客户端请求的服务器。

Similarly, when you install a server client (for example, [!DNL Insight] or [!DNL Report]) you must install the digital certificate that authorizes a named individual (for example, Jane Smith) to use the installed client application. 如果您需要将Adobe应用程序迁移到另一台计算机或其他指定用户，则必须从Adobe获取新证书。 为此，请与Adobe客户关怀联系。

客户端应用程序提供此数字证书以访问服务器组件。 服务器组件的管理员可以根据客户端证书中显示的通用名称或组织单位值限制对服务器资源的访问。

通过随 Adobe 应用程序一起安装的 X.509 数字证书，其客户端和服务器组件还可以通过安全套接字层 (SSL) 交换信息。SSL 使用公钥和私钥加密系统保证通过 HTTP 的传输安全。Adobe 的 SSL 实现支持 1024 位 RSA 密钥并使用 128 位 RC4 加密算法。

除了安全性，您安装的数字证书还用作许可证密钥，使您能够运行已安装的Adobe软件。 要正常工作，数字证书必须是节点锁定且为最新证书，否则应用程序不开始。

## 字符串加密 {#section-8abe6b2d95704d38a04137d5c4602f0b}

请参 [阅字符串加](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) 密以加密密码。

## 节点锁定证书 {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

节点锁定证书是已注册到安装该证书的计算机的数字证书。 节点锁定将证书与特定节点标识符（唯一标识特定计算机的值）永久关联。 要锁定您的证书，您的计算机必须具有对Adobe许可证服务器或有权访问许可证服务器的代理服务器的Internet访问权限。

If you are installing on a machine that cannot access the Internet, you must obtain and install a special pre-locked certificate as described in [Using Digital Certificates on Machines Without Internet Access](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

如果您安装在可以访问Internet的计算机上，则您首次开始Adobe产品时，数字证书会自动锁定节点。 锁定节点后，该证书不能用于任何其他计算机。 如果您需要将Adobe产品迁移到另一台计算机，则必须从Adobe获取新的已解锁证书。

## 最新证书 {#section-15aabaa8625c46edaa7436e1f3fc29c5}

除了节点锁定外，数字证书必须是最新的。 若要保持最新，必须定期（通常每隔 30 天，但具体情况可能依您与 Adobe 的协议而定）重新验证您的证书。如果您的计算机具有Internet访问权限，则重新验证过程是完全透明的。 您的Adobe产品会自动连接到许可证服务器，并在必要时重新验证证书。 如果计算机无法访问Internet，则需要按照以下部分中的说明手动安装更新的证书。

## Using Digital Certificates on Machines Without Internet Access {#section-809366329a7d4e198f95fe06c1f534fa}

If you are installing on a machine that cannot access the Internet, you must request a pre-locked certificate for your installation of [!DNL Insight Server]. 预锁定证书是Adobe手动锁定到计算机的节点标识符的数字证书。

要请求预先锁定的证书，您需要向Adobe客户服务中心发送节点标识符和证书编号。 要获取计算机的节点标识符，请与Adobe客户服务部门联系以请求Adobe节点标识符实用程序。 您还可以从Adobe软件尝试连接到许可证服务器时发出并且无法连接的警报中获取节点标识符。

When you receive the pre-locked certificate, install it as described in the last two steps of [Digital Certificate Installation Procedures](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). 当需要重新验证证书时，您必须从许可证服务器下载一个经过验证的新证书，然后在您的计算机上重新安装它。

## 数字证书的安装过程 {#section-19f31676aad344a98e26e4fca1fad03b}

**下载并安装数字证书**

1. 打开Web浏览器 [至https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >此时您的浏览器可能会提示您提供数字证书。 If it does, simply click **[!UICONTROL Cancel]** to dismiss the dialog box.

1. On the login screen, enter the **[!UICONTROL Account Name]** and the **[!UICONTROL Password]** that you received from Adobe, then click **[!UICONTROL login]**.

1. 找到为您颁发的证书， [!DNL Insight Server]然后单击与该证书关联的图标。

   >[!NOTE]
   >
   >记下分配给此证书的公用名称。 您在以后的步骤中使用此名称。

1. When prompted to save the certificate, click **[!UICONTROL Save]**. （请注意，文件名称与与证书关联的公用名称相匹配。）
1. 将文件下载到 [!DNL Certificates] 安装目录中的 [!DNL Insight Server] 文件夹中。This folder already contains a certificate file named [!DNL trust_ca_cert.pem]. 此证书文件必须始终存在。

1. 将下载的证书文件重命名为：

[!DNL server_cert.pem]

