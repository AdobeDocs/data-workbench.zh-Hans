---
description: 有关数字证书的常规信息及其下载和安装步骤。
solution: Analytics
title: 下载并安装数字证书
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: ht
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: ht
source-wordcount: '916'
ht-degree: 100%

---


# 下载并安装数字证书{#downloading-and-installing-the-digital-certificates}

有关数字证书的常规信息及其下载和安装步骤。

* [了解数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [节点锁定证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [最新证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [在没有 Internet 访问权限的计算机上使用数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [数字证书的安装步骤](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## 了解数字证书 {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe 使用 X.509 数字证书来标识和验证构成实施的客户端和服务器组件。

安装服务器组件（[!DNL Insight Server] 或 [!DNL Repeater]）时，必须安装 Adobe 颁发给该组件的数字证书。如果您需要将 Adobe 应用程序迁移到另一台计算机，则必须从 Adobe 获取新的证书。为此，请与 Adobe 客户关怀团队联系。

该证书上的通用名称可通过指定的域名（例如，[!DNL vs001a.mycompany.com]）来标识服务器。当服务器客户端连接到此服务器时，服务器将显示该证书，以验证它确实是客户端请求的服务器。

同样，安装服务器客户端（例如，[!DNL Insight] 或 [!DNL Report]）时，您必须安装数字证书，以授权指定人选（例如，Jane Smith）使用所安装的客户端应用程序。如果您需要将 Adobe 应用程序迁移到另一台计算机或另一个指定用户，则必须从 Adobe 获取新的证书。为此，请与 Adobe 客户关怀团队联系。

客户端应用程序提供此数字证书，以获得对服务器组件的访问权限。服务器组件管理员可根据客户端证书中显示的通用名称或组织单位值，限制对服务器资源的访问。

通过随 Adobe 应用程序一起安装的 X.509 数字证书，其客户端和服务器组件还可以通过安全套接字层 (SSL) 交换信息。SSL 使用公钥和私钥加密系统保证通过 HTTP 的传输安全。Adobe 的 SSL 实现支持 1024 位 RSA 密钥并使用 128 位 RC4 加密算法。

除了安全性，您安装的数字证书还将用作许可证密钥，支持您运行已安装的 Adobe 软件。为了正常运行，数字证书必须是节点锁定证书且为最新的证书，否则应用程序将无法启动。

## 字符串加密 {#section-8abe6b2d95704d38a04137d5c4602f0b}

请参阅[字符串加密](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a)，以对密码进行加密。

## 节点锁定证书 {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

节点锁定证书是已在安装该证书的计算机上进行注册的数字证书。节点锁定会永久性地将证书与特定节点标识符（唯一标识某台特定计算机的值）相关联。若要对您的证书执行节点锁定，您的计算机必须能够通过 Internet 访问 Adobe 许可证服务器，或者能够通过 Internet 访问拥有 Adobe 许可证服务器访问权限的代理服务器。

如果在无法访问 Internet 的计算机上进行安装，则必须获取并安装特殊的预锁定证书，如[在没有 Internet 访问权限的计算机上使用数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)中所述。

如果在可以访问 Internet 的计算机上进行安装，那么当首次启动 Adobe 产品时，您的数字证书将自动完成节点锁定。完成节点锁定后，该证书将无法在任何其他计算机上使用。如果您需要将 Adobe 产品迁移到另一台计算机，则必须从 Adobe 获取新的、未锁定的证书。

## 最新证书 {#section-15aabaa8625c46edaa7436e1f3fc29c5}

除了实现节点锁定之外，数字证书还必须是最新的。若要保持最新，必须定期（通常每隔 30 天，但具体情况可依据您与 Adobe 签署的协议而定）重新验证您的证书。如果您的计算机具有 Internet 访问权限，则重新验证过程将完全透明。您的 Adobe 产品会自动连接到许可证服务器，并在必要时重新验证证书。如果您的计算机没有 Internet 访问权限，则需要按照以下部分所述，手动安装更新的证书。

## 在没有 Internet 访问权限的计算机上使用数字证书{#section-809366329a7d4e198f95fe06c1f534fa}

如果安装在无法访问 Internet 的计算机上，则必须为您的 [!DNL Insight Server] 安装请求预锁定证书。预锁定证书是 Adobe 手动锁定到计算机节点标识符的数字证书。

若要请求预锁定证书，您需要将节点标识符和证书编号发送到 Adobe 客户关怀团队。若要获取您计算机的节点标识符，请联系 Adobe 客户关怀团队，以请求 Adobe 节点标识符实用工具。另外，您还可以从 Adobe 软件在尝试连接许可证服务器但无法连接时所发出的警告中获取节点标识符。

当您收到预锁定证书时，请按照[数字证书的安装步骤](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)中所述的最后两步进行安装。当需要重新验证证书时，您必须从许可证服务器上下载一个经过验证的新证书，并将其重新安装到您的计算机上。

## 数字证书的安装步骤 {#section-19f31676aad344a98e26e4fca1fad03b}

**要下载并安装数字证书，请执行以下步骤：**

1. 打开 Web 浏览器，以访问 [https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >此时，您的浏览器可能会提示您提供数字证书。如果是这样，请单击 **[!UICONTROL Cancel]** 以关闭该对话框。

1. 在“登录”屏幕上，输入您从 Adobe 收到的 **[!UICONTROL Account Name]** 和 **[!UICONTROL Password]**，然后单击 **[!UICONTROL login]**。

1. 找到为您的 [!DNL Insight Server] 颁发的证书，然后单击与该证书相关联的图标。

   >[!NOTE]
   >
   >记下分配给该证书的通用名称。您可以在之后的步骤中使用此名称。

1. 提示保存证书时，单击 **[!UICONTROL Save]**。（请注意，文件名称应当与证书关联的通用名称相匹配。）
1. 将该文件下载到 [!DNL Insight Server] 安装目录的 [!DNL Certificates] 文件夹中。此文件夹已包含一个名为 [!DNL trust_ca_cert.pem] 的证书文件。该证书文件必须始终存在。

1. 将下载的证书文件重命名为：

[!DNL server_cert.pem]

