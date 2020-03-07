---
description: 有关使用自定义证书的说明。
title: 使用 Data Workbench 中的自定义证书
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# 使用 Data Workbench 中的自定义证书{#using-custom-certificates-in-data-workbench}

有关使用自定义证书的说明。

Data Workbench 客户端或服务器使用的证书需要由受信任的 CA（证书颁发机构）签名。Data Workbench 客户会收到由 Visual Sciences CA 签名的证书。这些证书受到 Data Workbench 软件的信任，因为 [!DNL trust_ca_cert.pem]（随 Insight 软件一起提供，并存储在服务器和客户端的 **Certificates** 目录中）包含 Visual Sciences CA 的&#x200B;*根 CA 证书*。当客户端和服务器使用 SSL 相互通信时，这些证书可同时用于软件和身份验证的授权。只有 Visual Sciences CA 颁发的证书才可用于授权，但是其他证书有可能被用于通信和身份验证。在下列情况中，由非 Visual Sciences 的 CA 颁发的证书被称为&#x200B;*自定义证书*。

**重要说明：**&#x200B;对于服务器和客户端，Data Workbench 软件使用客户端中安装的证书文件，或服务器 **Certificates** 目录中的证书，或在其配置中明确标识的证书。然而，您还可以使用[适用于客户端的 Windows 证书存储区](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d)。

以下说明介绍了使用自定义证书在 Data Workbench 客户端和服务器之间通信时应遵循的流程。并非必须顾及到每一个细节，可在流程中采取不同的变通方式。但是，以下流程是经过测试并证明有效的。

## 设置自定义客户端证书 {#section-2083fd41973e451fa404e7a4ae4da591}

1. 将发证 CA 的证书添加到 [!DNL trust_cert_ca.pem]，该文件安装在客户端的 **Certificates** 目录中，以及可使用此自定义证书访问的每个聚类内每个服务器的目录中。

1. 获取聚类中每个服务器的自定义证书，这些证书具有以下条件：

   1. Certificate is formatted as a [!DNL .pem] certificate.
   1. 证书包含其私钥，并且未被加密（例如，它没有密码/密码短语）。

      证书包含其私钥，并且具有以下行之一：

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      One way to remove the password phrase from a [!DNL .pem] certificate:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Certificate 具有 CN、O、OU 等，这是根据服务器的 [!DNL Access Control.cfg] 文件中此客户端的要求来决定的。
   1. 证书是通过 *client*（或 *server* **和** *client*）的 *purpose **** 颁发的。

      要验证证书具有服务器和/或客户端的目的代码，可使用以下命令：

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      对于服务器证书，两个命令都应产生 OK：

      ```
      custom_communications_cert.pem: OK
      ```

      对于客户端证书，只需第二个命令产生 [!DNL OK]。

1. 将证书置于客户端的 **Certificates** 目录中。
1. 在您希望使用此证书的每个聚类 [!DNL Insight.cfg]serverInfo 下方的 ** 中，确保&#x200B;*自定义客户端证书*&#x200B;已命名，例如：

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Setting up Custom Server Certificates {#setting-up-custom-server-certificates}

此部分假设您拥有一个已设置并运行的聚类，它使用 Visual Sciences 颁发的证书，并且其配置遵循普通规则（例如主服务器上的 *Components for Processing Servers* 目录被同步到所有 DPU 的 *Components* 目录）。

1. 将发证 CA 的证书添加到 [!DNL trust_cert_ca.pem]，该文件安装在聚类中的每个服务器上，以及需要与此聚类通信的每个客户端上。
1. 获取聚类中每个服务器的自定义证书，这些证书具有以下要求：

   1. Custom certificate is formatted as a [!DNL .pem] certificate.
   1. 证书包含其私钥，并且未被加密（例如，它没有密码/密码短语）。

      当证书具有类似下面的行时，需要包含其私钥：

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      One way to remove the password phrase from a [!DNL .pem] certificate:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. 证书具有与当前安装在服务器上的 [!DNL server_cert.pem] 相同的 CN。
   1. 证书是为了用于 *server* 和 *client* 的目的而颁发的。

      要验证证书具有服务器和/或客户端的目的代码，可使用以下命令：

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      对于服务器证书，两个命令都应产生 OK：

      ```
      custom_communications_cert.pem: OK
      ```

      对于客户端证书，只需第二个命令产生 [!DNL OK]。

1. 在服务器的 **Certificates** 目录中安装每个服务器的自定义证书，其名称为 [!DNL custom_communications_cert.pem]。

1. 使用文本编辑器，将以下行同时添加到 **Components** 和 *Components for Processing Servers* 目录的 *Communications.cfg* 文件中，它们位于第一行  ([!DNL component = CommServer]) 的正下方：

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. 重新启动所有服务器。

**关于证书失败的警告**

当 Insight 服务器或客户端在 **Certificates** 目录中查找&#x200B;**许可证**&#x200B;证书时，它会尝试验证所有的证书（除 [!DNL trust_ca_cert.pem] 之外）是否存在 Insight CA 证书的硬编码副本，但是对于目录中存在的任何自定义证书而言，将出现验证失败的结果。服务器会发出下面的警告：

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

您可以放心地忽略此警告。
