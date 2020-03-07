---
description: Adobe 使用 X.509 数字证书标识和验证构成实施的客户端和服务器组件。
solution: Analytics
title: 了解数字证书
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解数字证书{#understanding-digital-certificates}

Adobe 使用 X.509 数字证书标识和验证构成实施的客户端和服务器组件。

安装 [!DNL Report Server] 时，您必须安装数字证书，以授权指定人选（例如，Jane Smith）使用所安装的客户端应用程序。

>[!NOTE]
>
>If you need to migrate [!DNL Report Server] to another machine or another named user, you must obtain a new certificate from Adobe. 为此，请与Adobe客户关怀联系。

[!DNL Report Server] 提供此数字证书以获得对服务器组件的访问权限。服务器组件的管理员可以根据客户端证书中显示的通用名称或单位值限制对服务器资源的访问。

通过随 Adobe 应用程序一起安装的 X.509 数字证书，其客户端和服务器组件还可以通过安全套接字层 (SSL) 交换信息。SSL 使用公钥和私钥加密系统保证通过 HTTP 的传输安全。Adobe 的 SSL 实现支持 1024 位 RSA 密钥并使用 128 位 RC4 加密算法。

In addition to security, the digital certificate that you install also functions as a license key that enables you to run the installed [!DNL Report Server]. 若要正常工作，数字证书必须是节点锁定证书且为最新，否则应用程序将无法启动。

## 节点锁定证书 {#section-3338f1558e7844888dced8f395888744}

节点锁定证书是已注册到安装该证书的计算机的数字证书。 节点锁定将证书与特定节点标识符（唯一标识特定计算机的值）永久关联。 要将证书锁定到节点，您的计算机必须具有对Adobe许可证服务器或有权访问许可证服务器的代理服务器的Internet访问权限。

If you are installing on a machine that cannot access the Internet, you must obtain and install a special pre-locked certificate as described in [Using Digital Certificates on Machines Without Internet Access](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) on this page.

If you are installing on a machine that can access the Internet, your digital certificate is node-locked automatically the first time that you start [!DNL Report Server]. 锁定节点后，该证书无法用于任何其他计算机。 If you need to migrate [!DNL Report Server] to another machine, you must obtain a new, unlocked certificate from Adobe.

## 最新证书 {#section-b4053ab714514dfb97ea7f61bbb8da1e}

除了节点锁定外，数字证书必须是最新的。 要保持最新，您的证书必须定期（通常每30天重新验证一次，但可能因您与Adobe的协议而异）。 如果您的计算机可以访问Internet，则重新验证过程完全透明。 [!DNL Report Server] 自动连接到许可证服务器并在必要时重新验证证书。如果您的计算机无法访问Internet，则需要按照以下部分所述手动安装更新的证书。

## Using Digital Certificates on Machines Without Internet Access {#section-18cce05e2204407bb2b6b75deab9197d}

If you are installing on a machine that cannot access the Internet, you must request a pre-locked certificate for your installation of [!DNL Report Server]. 预锁定证书是Adobe手动锁定到计算机节点标识符的数字证书。

要请求预先锁定的证书，您需要将节点标识符和证书编号发送给Adobe客户服务。 要获取计算机的节点标识符，请与Adobe客户关怀部门联系以请求Adobe实用程 [!DNL Node Identifier] 序。 还可以从 [!DNL Report Server] 尝试连接到许可证服务器但无法连接时发出的警告中获取节点标识符。When you receive the pre-locked certificate, install it as described in the last two steps of [Digital Certificate Installation Procedures](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

当需要重新验证证书时，您必须从许可证服务器下载一个新的已验证证书，然后在您的计算机上重新安装它（除非您与Adobe的协议另有规定）。
