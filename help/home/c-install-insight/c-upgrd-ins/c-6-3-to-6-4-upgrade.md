---
description: 按照这些步骤升级至 Data Workbench v6.4。
title: 将 6.3 升级至 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# 将 6.3 升级至 6.4{#upgrading-to}

按照这些步骤升级至 Data Workbench v6.4。

## 升级要求和建议 {#section-8704a9ac358246cd81233dd0982d534f}

请在升级到 Data Workbench 6.4 时，遵循下面的要求和建议。

>[!IMPORTANT]
>
>建议您使用新安装的默认配置文件并自定义它们，而不是从以前的安装中移动文件，但以下除外：

* 为下列可执行文件&#x200B;**添加** ***Windows Server 2012 中 MS 系统中心终端保护***&#x200B;的&#x200B;*已排除进程*：

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   该操作可以为这些界面可执行文件提供“白名单”权限。

* **更新服务器上的&#x200B;*Trust_ca_cert.pem*证书**。
* **重新组织归因配置文件**。

   * The *Attribution* folder was renamed to ***Attribution - Premium*** (found in the default installation at *Profiles*\*Attribution - Premium*).

   * 删除了 *Premium* 配置文件，并将工作区移至新增的 ***Attribution - Premium*** 文件夹。

* **更新&#x200B;*Attribution - Premium*设置**。如果您使用覆盖默认 *Adobe SC* 配置文件的参数设置对配置文件进行了自定义，则需要更新这些配置文件中的自定义字段：

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* 由于经过此次重新组织，您需要从服务器安装中删除旧的 *Attribution* 和 *Premium* 文件夹。

   **将以下设置**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   更改为：

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **更新自定义的 Meta.cfg 文件**（如有必要）。

   The **[!DNL Meta.cfg]** files in **[!DNL Base\Context and AdobeSC\Context]** folders have been updated in this release.

   如果您在安装期间覆盖了 **meta.cfg** 文件，则需要通过适当地输入这些参数以及&#x200B;**元数据矢量**，来更新您的配置文件副本：

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **设置 Report Server 权限**，以便在 Windows Server 2012 上生成 Microsoft Excel 报表。

   1. Set permission of the root folder (**[!DNL E:\ReportServer\]**) to *Everyone = full control*.

   1. 使用适当的权限，创建下面的文件夹：

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >如果在Windows Server 2012上运行Report Server，则需要安装Windows Server 2012 R2。

   1. 指派“SYSTEM”作为这些文件夹的所有者。

* **向 Report Server 添加字体。** 在**[!DNL ReportServer.cfg]**文件中，添加以下字体（适用于所有语言）:

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **更新您的Microsoft Excel **（如有必要）。

   随着 Data Workbench 6.4 的发布，对 Excel 2007 的支持已经终止。此外，由于 Data Workbench 只能在 Microsoft Windows 的 64 位体系结构中运行，因此建议您同时安装 Microsoft Excel 的 64 位版本。

* 安装工作站（客户端）要求具备 **64 位体系结构**。
* **运行工作站安装向导**。

   通过下载并启动 ***InsightSetup.exe***，然后遵循安装向导分步执行操作，完成工作站（客户端）新版本的安装。默认情况下，安装向导会将您的文件安装到新的位置：

   默认情况下，程序文件现在保存于下列位置：

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   默认情况下，数据文件（配置文件、证书、跟踪日志和用户文件）现在保存于下列位置：

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **向工作站添加字体**。

   在 **[!DNL Insight.cfg]** 文件中，添加下面的字体（适用于所有语言）：

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

