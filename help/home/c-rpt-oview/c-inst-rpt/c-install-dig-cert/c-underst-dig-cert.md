---
description: Adobe 使用 X.509 数字证书来标识和验证构成实施的客户端和服务器组件。
title: 了解数字证书
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 69%

---

# 了解数字证书{#understanding-digital-certificates}

{{eol}}

Adobe 使用 X.509 数字证书来标识和验证构成实施的客户端和服务器组件。

安装 [!DNL Report Server] 时，您必须安装数字证书，以授权指定人选（例如，Jane Smith）使用所安装的客户端应用程序。

>[!NOTE]
>
>如果需要迁移 [!DNL Report Server] 对于其他计算机或其他指定用户，必须从Adobe获取新证书。 为此，请与 Adobe 客户关怀团队联系。

[!DNL Report Server] 提供此数字证书以获得对服务器组件的访问权限。服务器组件管理员可根据客户端证书中显示的通用名称或组织单位值，限制对服务器资源的访问。

通过随 Adobe 应用程序一起安装的 X.509 数字证书，其客户端和服务器组件还可以通过安全套接字层 (SSL) 交换信息。SSL 使用公钥和私钥加密系统保证通过 HTTP 的传输安全。Adobe 的 SSL 实现支持 1024 位 RSA 密钥并使用 128 位 RC4 加密算法。

除了安全性，您安装的数字证书还用作许可证密钥，用于运行已安装的 [!DNL Report Server]. 若要正常工作，数字证书必须是节点锁定证书且为最新，否则应用程序将无法启动。

## 节点锁定证书 {#section-3338f1558e7844888dced8f395888744}

节点锁定证书是已在安装该证书的计算机上进行注册的数字证书。节点锁定会永久性地将证书与特定节点标识符（唯一标识某台特定计算机的值）相关联。若要对您的证书执行节点锁定，您的计算机必须能够通过 Internet 访问 Adobe 许可证服务器，或者能够通过 Internet 访问拥有 Adobe 许可证服务器访问权限的代理服务器。

如果安装在无法访问Internet的计算机上，则必须获取并安装特殊的预锁定证书，如 [在没有Internet访问权限的计算机上使用数字证书](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) 在此页面上。

如果安装在可以访问Internet的计算机上，则在您首次启动时，您的数字证书将自动锁定到节点 [!DNL Report Server]. 完成节点锁定后，该证书将无法在任何其他计算机上使用。如果需要迁移 [!DNL Report Server] 到另一台计算机，必须从Adobe中获取新的已解锁证书。

## 最新证书 {#section-b4053ab714514dfb97ea7f61bbb8da1e}

除了实现节点锁定之外，数字证书还必须是最新的。若要保持最新，必须定期(通常每30天，但具体情况可能因您与Adobe的协议而异)重新验证您的证书。 如果您的计算机具有 Internet 访问权限，则重新验证过程将完全透明。[!DNL Report Server] 自动连接到许可证服务器并在必要时重新验证证书。如果您的计算机没有 Internet 访问权限，则需要按照以下部分所述，手动安装更新的证书。

## 在没有 Internet 访问权限的计算机上使用数字证书 {#section-18cce05e2204407bb2b6b75deab9197d}

如果安装在无法访问 Internet 的计算机上，则必须为您的 [!DNL Report Server] 安装请求预锁定证书。预锁定证书是 Adobe 手动锁定到计算机节点标识符的数字证书。

若要请求预锁定证书，您需要将节点标识符和证书编号发送到 Adobe 客户关怀团队。要获取您计算机的节点标识符，请联系Adobe客户关怀团队以请求Adobe [!DNL Node Identifier] 工具。 还可以从 [!DNL Report Server] 尝试连接到许可证服务器但无法连接时发出的警告中获取节点标识符。当您收到预锁定证书时，请按照[数字证书的安装步骤](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d)中所述的最后两步进行安装。

当需要重新验证证书时，您必须从许可证服务器下载一个经过验证的新证书，并将其重新安装到您的计算机上(除非您与Adobe状态另有协议)。
