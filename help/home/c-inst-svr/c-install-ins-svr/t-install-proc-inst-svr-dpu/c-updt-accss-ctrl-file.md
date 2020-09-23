---
description: 访问控制.cfg文件管理对Insight Server中某些功能的访问。
solution: Analytics
title: 更新访问控制文件
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 4%

---


# 更新访问控制文件{#updating-the-access-control-file}

访问控制.cfg文件管理对Insight Server中某些功能的访问。

它定义名为AccessGroups的实体。 AccessGroup标识一组用户，这些用户具有使用服务器特定功能的权限。

在与连接之 [!DNL Insight Server] 前， [!DNL Insight]必须更新管理员访问组，以包含Adobe向您的组 [!DNL Insight] 织颁发的一个许可证。 此AccessGroup标识允许通过执行管理功能的用户 [!DNL Insight]。

以下过程介绍如何向Administrators AccessGroup添加许可证。 要完成此任务，您必须确定哪个许 [!DNL Insight] 可证对您的组织具有管理权限。 (对于初始设置和配置，为单个许可证授予管理权限就足够了。 您可以稍后为其他许可证授予管理权限。) 您还需要知道分配给此许可证的“通用名称”。 要获得此值，可在https://aap.adobe.com检查您帐户的许可证 [书](https://aap.adobe.com)。

此过程的目的只是标识一个许可副本，您 [!DNL Insight] 可以使用它进行初始设置和配置 [!DNL Insight Server]。 识别此许可证后，您可以使用的许可副本执行所有后续服务器配置（包括其他AccessGroup配置） [!DNL Insight]。 有关使用AccessGroups控制对服务器的访问的其他信息，请参 [阅配置访问控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。

**更新访问控制文件**

1. 导览至安 [!DNL Access Control] 装目录中的文件夹 [!DNL Insight Server]。

   示例：[!DNL C:\Adobe\Server\Access Control]

1. 在文本 [!DNL Access Control.cfg] 编辑器（如记事本）中打开文件。
1. 在Administrators AccessGroup中找到CN条目，并将此条目的现有值替换为通用名称，该通用名称标识 [!DNL Insight] 您最初用于设置和管理的名称 [!DNL Insight Server]。 以下文件片段说明在文件中插入通用名称的 [!DNL Access Control.cfg] 位置。

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

   如果您使用基于凭据的身份验证，将有一些额外条目可供配置。 这些条目包括：

   * O（组织ID）:此条目表示组织的ID。 例如：`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。可以在Admin Console中找到此ID。
   * PLC —— 此条目允许访问为特定产品配置设置的用户。 它可以用于格式 `Organization_Id-PLC`。 例如：`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。使用PLC为Data Workbench设置的用户 `DataworkbenchAdminUsers` 将获得对其服务器的访问权。
   * 电子邮件——此条目允许访问任何个人用户。 其值应为提供用户的电子邮件地址。 例如：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 条目区分大小写。 必须确保为O、PLC和电子邮件指定的值与Admin Console中显示的值完全相同。
   >    * 键入与在证书上显示完全相同的通用名称。
   >    * 请勿使用Tab键在文件(或Adobe组 [!DNL Access Control.cfg] 件的任何其他配置文件)中生成空白。 仅使用空格创建空格。 制表符可防止系统正确读取文件。


1. 保存并关闭该文件。

