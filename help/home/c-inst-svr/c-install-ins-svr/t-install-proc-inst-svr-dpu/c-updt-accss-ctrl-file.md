---
description: Access Control.cfg文件可管理对Insight Server中某些功能的访问。
title: 更新访问控制文件
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 4%

---

# 更新访问控制文件{#updating-the-access-control-file}

{{eol}}

Access Control.cfg文件可管理对Insight Server中某些功能的访问。

它定义名为AccessGroups的实体。 AccessGroup标识一组有权使用服务器某些功能的用户。

在连接到之前 [!DNL Insight Server] with [!DNL Insight]，则必须更新管理员访问组以包含 [!DNL Insight] Adobe颁发给贵组织的许可证。 此AccessGroup标识允许通过执行管理功能的用户 [!DNL Insight].

以下过程介绍如何向管理员访问组添加许可证。 要完成此任务，必须确定 [!DNL Insight] 许可证拥有您组织的管理权限。 (对于初始设置和配置，向单个许可证授予管理权限就足够了。 您可以稍后为其他许可证授予管理权限。) 您还需要知道分配给此许可证的“通用名称”。 要获取此值，您可以在 [https://aap.adobe.com](https://aap.adobe.com).

此过程的目的只是为了确定 [!DNL Insight] 用于初始设置和配置 [!DNL Insight Server]. 在您识别此许可证后，您可以使用的授权副本执行所有后续服务器配置（包括其他AccessGroup配置） [!DNL Insight]. 有关使用AccessGroups控制对服务器的访问的其他信息，请参阅 [配置访问控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**更新访问控制文件**

1. 导航到 [!DNL Access Control] 文件夹。 [!DNL Insight Server].

   示例：[!DNL C:\Adobe\Server\Access Control]

1. 打开 [!DNL Access Control.cfg] 文件（如记事本）。
1. 在Administrators AccessGroup中找到CN条目，并将此条目的现有值替换为标识 [!DNL Insight] 用于初始设置和管理 [!DNL Insight Server]. 以下文件片段说明了在 [!DNL Access Control.cfg] 文件。

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   如果您使用基于凭据的身份验证，则可以额外使用一些条目进行配置。 这些条目包括：

   * O（组织ID）：此条目表示组织的ID。 例如：`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。此ID可在Admin Console中找到。
   * PLC — 此条目允许访问针对特定产品配置设置的用户。 它可用于格式 `Organization_Id-PLC`. 例如：`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。使用PLC设置Data Workbench的用户 `DataworkbenchAdminUsers` 将在其服务器上获取访问权限。
   * 电子邮件 — 此条目允许访问任何个人用户。 其值应为已配置用户的电子邮件地址。 例如：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 条目区分大小写。 您必须确保为O、PLC和电子邮件指定的值与Admin Console中显示的值完全相同。
   >    * 键入与证书上显示的名称完全相同的通用名称。
   >    * 请勿使用Tab键在 [!DNL Access Control.cfg] 文件(或Adobe组件的任何其他配置文件中)。 仅使用空格创建空格。 制表符阻止系统正确读取文件。


1. 保存并关闭该文件。
