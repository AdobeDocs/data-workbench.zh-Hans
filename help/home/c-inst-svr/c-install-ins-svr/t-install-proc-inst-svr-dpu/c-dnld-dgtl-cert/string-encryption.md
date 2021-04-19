---
description: 客户端与服务器之间进行通信时，加密密码和其他字符串。
title: 字符串加密
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
translation-type: ht
source-git-commit: 233b04c65a45d3f92b8670bc244b907dc198b51d
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---

# 字符串加密{#string-encryption}

客户端与服务器之间进行通信时，加密密码和其他字符串。

Data Workbench 客户端（工作站）与服务器进行通信时，您可以保存具有 *EncryptedString* 类型的值参数（例如密码）。此操作可隐藏参数，并通过返回的相应私钥将字符串保存到服务器上的 *Windows 凭据存储区*。此操作主要存储导出中使用的凭据，但可用于加密任何参数。

* 新文件夹被添加在 Server\**EncryptStrings** 路径下。

   在此，您可以设置配置文件以加密字符串。

* 新的配置文件被添加在 Server\Component\**EncryptedStrings.cfg** 路径下。

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   此文件可轮询 *Server*\*EncryptStrings* 文件夹中的加密配置文件。

**加密字符串**：

1. 为具有以下字段集的字符串创建 **EncryptedStrings.cfg** 配置文件：

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Value* - 此字段包含需要加密的纯文本。

      它只是服务器端加密。*Value* 设置仅在服务器计算机上加密。

   * *Name* - 此字段包含可标识加密字符串的值。
   * *EncryptValue* - 此字段将在输入配置文件中保留为空。在此字段中将返回加密的值。

   您可以为不同的字段添加多个 **NameEncryptValuePair** 值以进行加密。

   >[!NOTE]
   >
   >所有空白值字段都将被删除。

1. 将 **EncryptedStrings.cfg** 文件保存至 Server\**EncryptStrings** 文件夹。

**输出文件**

将会生成与输入文件（名称为 &lt;*文件名*>）同名的输出文件。*加密*&#x200B;扩展。例如，如果输入文件名称为 *sample.cfg*，则输出文件将命名为 *sample.cfg.encrypted*。
