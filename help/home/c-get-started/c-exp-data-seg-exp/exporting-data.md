---
description: 您现在可以借助 FTP 和 SFTP 协议，用 CSV、TSV、区段导出和带标题区段导出，将区段文件从客户端（工作站）导出到服务器。
title: 使用S/FTP交付导出区段
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# 使用S/FTP交付导出区段{#export-a-segment-using-s-ftp-delivery}

您现在可以借助 FTP 和 SFTP 协议，用 CSV、TSV、区段导出和带标题区段导出，将区段文件从客户端（工作站）导出到服务器。

**设置“S/FTP 导出”配置文件**

要设置导出配置，必须添加两个新的导出配置文件，用于设置 FTP 或 SFTP 连接，以便从 *FTPServerInfo.cfg* 文件收集服务器详细信息，并且从 *FTPUserCredentials* 文件夹收集凭证（对应于命令参数中给定的服务器名称）。

* 设置 **FTPServerInfo.cfg** 文件。

   输入 FTP 服务器信息并设置工作站允许的连接重试次数。Edit from the workstation or the server at [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]** file.

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* 设置 **FTPUserCredentials.cfg** 文件。

   Enter user credentials to connect to servers using the [!DNL Server\Admin\Export\] **[!DNL FTPUserCredentials.cfg]** file. 此文件包含连接服务器所必需的用户凭证，并且只能从服务器进行编辑，不能从工作站（客户端）进行编辑。

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >确保您为验证生成的SSH密钥的格式与使用SSH Keygen命令生成的密钥的格式相同。
   >
   >使用 keygen 生成 SSH 密钥的示例：
   >
   >```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   **FTPUserCredentials.cfg** 文件中包含各类 FTP 或 SFTP 传输所必需的六个参数。

   1. *用户名*
   1. *User Password*
   1. *Server Name*
   1. *Public Key Path*
   1. *私有密钥路径*
   1. *密码短语*
   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 协议 </th> 
      <th colname="col2" class="entry"> 参数 </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>设置参数 1、2、3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP（使用密码验证） </p> </td> 
      <td colname="col2"> <p>传输时如使用密码验证（在命令参数中使用 -p），则设置参数 1、2、3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP（使用密钥验证） </p> </td> 
      <td colname="col2"> <p>传输时如使用密钥验证（在命令参数中使用 -k），则设置参数 1、2、3、4、5、6。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

**设置 FTP 和 SFTP 导出命令**

1. 打开导出表。

   从工作站中，右键单击&#x200B;*明细表*&#x200B;并选择一种导出类型 - CSV、TSV、区段导出或带标题区段导出。或者，从命 [!DNL .export] 令提示符下打开文件并进行编辑(请参阅 [配置导出区段](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372))。

1. 在&#x200B;*命令*&#x200B;字段中，设置为指向导出可执行文件：

   ```
   ExportIntegration.exe
   ```

1. 根据所要求的协议和验证方法的不同，将&#x200B;*命令参数*&#x200B;字段设置为以下几种样式：

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP**（如使用密码进行验证）

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP**（如使用密钥进行验证）

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

所有命令参数都必须输入，且输入时必须遵循上述要求。

## S/FTP export using private/public keys {#section-0534424d79a54a47b82594cfa7b3c17f}

若要使用私有密钥/公共密钥进行 FTP 和 SFTP 导出，请将配置文件放置在以下这些文件夹中：

* Place **FTPServerInfo.cfg** in the [!DNL Server/Addresses/Export/] folder.
* Place **FTPUserCredentials.cfg** in the [!DNL Server/Admin/Export/] folder.

**FTPServerInfo.cfg** 文件包含下面六个参数：

1. *User Name*
1. *User Password*
1. *Server Name*
1. *Public Key Path*
1. *Private Key Path --* 将私有密钥路径放置在没有扩展名的配置文件中，例如：

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Passphrase*

FTP使用参数1、2和3。

SFTP在传输使用密码身份验证时使用参数1、2和3。

如果传输期间需要进行密钥验证，那么 SFTP 将使用所有这六个参数。例如，若要使用密钥进行验证：

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

配置文件必须位于正确位置。

>[!NOTE]
>
>The public keys need to point to a **.pem** file and not to a folder location. 您可以使用各种应用程序（例如，Cygwin）中的 SSH 密钥生成函数来创建密钥。（Putty 生成的 .ppk 格式的密钥不受支持。）
