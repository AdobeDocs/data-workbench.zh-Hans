---
description: 您可以将客户端的证书和私钥存储在 Windows 证书存储区，以便与服务器进行 SSL 通信。
title: Windows 证书存储
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: ht
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: ht
source-wordcount: '1000'
ht-degree: 100%

---


# Windows 证书存储{#windows-certificate-store}

您可以将客户端的证书和私钥存储在 Windows 证书存储区，以便与服务器进行 SSL 通信。

适用于客户端的 Windows 证书存储是一项新功能，该功能允许您将 SSL 通信证书和私钥存储在 Windows 证书存储区而非 `Insight/Certificates/<CertName>.pem` 文件中。如果您将证书存储区用于其他应用程序并希望在同一位置管理证书，或者，将证书存储区用于那些希望享用 Windows 证书存储区提供的额外 Windows 审核日志记录服务的用户，那么使用 Windows 证书存储区会是一种较适合的选择。

>[!NOTE]
>
>许可证服务器的授权功能仍将通过使用现有的 `<Common Name>.pem` 文件来维护，并且从证书存储区获得的证书将只能用于同您指定的服务器通信。

## 先决条件 {#section-69b18600052145ff8e5299b7123e69c5}

1. 您必须具有 [!DNL certmgr.msc] 文件的访问权限，并且能够将证书和密钥导入 **Personal** 存储区。（对于大部分 Windows 用户而言，默认情况下应当将其设置为 True。）

1. 执行配置的用户必须具有 **OpenSSL** 命令行工具的副本。
1. 必须将服务器和客户端配置为使用自定义 SSL 证书，如[使用自定义证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)中所述，它指明了如何将客户端证书存储在 Windows 证书存储区，而不是存储在 **Certificates** 目录中。

## 配置 Windows 证书存储区 {#section-3629802122e947d4b4f63e8b732cfe27}

可通过以下步骤启用适用于客户端的 Windows 证书存储区：

**步骤 1：将用户的 SSL 证书和私钥导入 Windows 证书存储区。**

在[使用自定义证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)中，为您提供了如何将 SSL 证书和密钥放入以下目录的指导说明：

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

证书的名称为 `<Common Name>.pem`（如 [!DNL Analytics Server 1.pem]（不是 [!DNL trust_ca_cert.pem] 文件)）。

在可以导入证书和私钥之前，必须先将它们从 [!DNL pem] 格式转化为 [!DNL .pfx] 格式（如 [!DNL pkcs12.pfx]）。

1. 打开命令提示符或终端，然后导航至目录：

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
   ```

1. 通过以下参数（以及实际的 [!DNL .pem] 文件名）运行 [!DNL openssl]：

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   如果出现系统提示，请按 **Enter** 以跳过输入导出密码的步骤。

1. 从运行提示符、开始菜单或命令行中运行 [!DNL certmgr.msc]。
1. 打开当前用户的 **Personal** 证书存储区。

   ![](assets/6_5_crypto_api_0.png)

1. 右键单击 **Certificates**，然后单击&#x200B;**所有任务** > **导入**。

   请确保已选中&#x200B;**当前用户**&#x200B;选项，然后单击&#x200B;**下一步**。

   ![](assets/6_5_crypto_api_4.png)

1. 单击&#x200B;**浏览**，并选择您此前创建的 `<CommonName>.pfx` 文件。为了进行查看，您需要将 X.509 证书的文件扩展下拉框更改为&#x200B;**个人信息交换**&#x200B;或&#x200B;**所有文件**。

   选择文件并单击&#x200B;**打开**，然后单击&#x200B;**下一步**。

1. 请不要输入密码，并确保只选中了&#x200B;**标志此密钥为可导出的密钥**&#x200B;和&#x200B;**包括所有扩展属性**&#x200B;选项。

   ![](assets/6_5_crypto_api_3.png)

   单击&#x200B;**下一步**。

1. 确保选中&#x200B;**将所有的证书都放入下列存储**，并且所列出的证书存储区为 **Personal**。（如果您是高级用户，可在此时选择其他存储区，但是您需要在以后更改配置。）

1. 单击&#x200B;**下一步**，然后单击&#x200B;**完成**。您应该会看到一个已成功导入的对话框，并且会在存储区的 Certificate 文件夹中发现您的证书。

   >[!NOTE]
   >
   >请特别留意&#x200B;**颁发给**&#x200B;和&#x200B;**颁发者**&#x200B;字段。下面的步骤将需要使用这些字段。

**步骤 2：编辑 Insight.cfg 文件。**

必须编辑 [!DNL Insight.cfg] 文件，以便指示 Data Workbench 使用 Windows 证书存储区功能。此文件中的每一个服务器条目都必须指定一些额外的参数。如果忽略这些参数，工作站将默认使用现有的证书配置。如果指定了参数但具有不正确的值，工作站则会进入错误状态，您必须参考日志文件以了解错误信息。

1. 打开 **Insight.cfg** 文件（位于 **Insight** 安装目录中）。

1. 向下滚动到您要配置的服务器条目。如果您要将 Windows 证书存储区应用于每个服务器，则必须对 [!DNL serverInfo] 对象矢量中的每个条目进行此类修改。
1. 将这些参数添加到他们的 [!DNL Insight.cfg] 文件。您可以在工作站中执行这一操作，或通过将以下参数添加到 [!DNL serverInfo] 对象来手动执行操作。（请确保使用空格而不是制表符，并且不要在此文件中出现其他录入或语法错误。）

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   布尔值可启用或禁用此功能。证书名称与证书管理器中的&#x200B;**颁发给**&#x200B;匹配。证书颁发者名称与&#x200B;**颁发者**&#x200B;匹配，而&#x200B;**存储区名称**&#x200B;必须匹配证书存储区名称。

   >[!NOTE]
   >
   >证书管理器 (certmgr.msc) 中的名称“Personal”实际上是指名为&#x200B;**“My”的证书存储区。**&#x200B;因此，如果您将 SSL 通信证书和私钥 (.PFX) 导入建议的 **Personal** 证书存储区，则必须将 **SSL CryptoAPI 证书存储区名称**&#x200B;字符串设置为“My”。将此参数设置为“Personal”并不会起作用。这是 Windows 证书存储区的特性。

   可在此获取有关预定义系统存储区的完整列表：[https://msdn.microsoft.com/zh-cn/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/zh-cn/library/windows/desktop/aa388136%28v=vs.85%29.aspx)。您的系统可能具有额外的证书存储区。如果您要使用的存储区不是“Personal”（例如 **My**），则必须获取证书存储区的规范名称，并在 [!DNL Insight.cfg] 文件中提供该名称。（Windows 文档对于系统存储区名称“My”的引用不一致，有时为“My”，有时为“MY”。此参数似乎不区分大小写。）

1. 在添加了这些参数并验证值与 Windows 证书管理器中的列表匹配后，保存 [!DNL Insight.cfg] 文件。

您现在即可启动工作站（或者与服务器断开连接/重新连接）。Data Workbench 应当从证书存储区加载您的证书和私钥，并正常连接。

## 日志输出 {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

当未找到证书或证书无效时，会在 [!DNL HTTP.log] 文件中引发此错误消息。

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>通过设置 [!DNL L4.cfg] 文件可启用 L4 记录框架（请查看您的帐户管理器，以执行相应设置）。
