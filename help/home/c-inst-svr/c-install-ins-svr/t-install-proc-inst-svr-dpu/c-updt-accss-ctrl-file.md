---
description: Access Control.cfg文件用于管理对Insight Server中某些功能的访问。
title: 更新访问控制文件
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: 5ce5b8f8b35d2d4f319076f54347e300e5f133df
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 4%

---

# 更新访问控制文件{#updating-the-access-control-file}

{{eol}}

Access Control.cfg文件用于管理对Insight Server中某些功能的访问。

它定义称为AccessGroups的实体。 AccessGroup标识一组有权使用服务器某些功能的用户。

在可以连接到 [!DNL Insight Server] 替换为 [!DNL Insight]，您必须更新管理员访问组以包含其中一个 [!DNL Insight] Adobe颁发给贵组织的许可证。 此AccessGroup标识允许通过执行管理功能的用户 [!DNL Insight].

以下过程介绍了如何将许可证添加到Administrator AccessGroup。 要完成此任务，您必须确定 [!DNL Insight] 许可证对您的组织具有管理权限。 (对于初始设置和配置，向单个许可证授予管理权限就足够了。 您可以稍后向其他许可证授予管理权限。) 您还需要知道分配给此许可证的“通用名称”。

此过程的目的只是为了标识以下项的许可副本： [!DNL Insight] 可用于初始设置和配置的插件 [!DNL Insight Server]. 一旦标识了此许可证，您就可以使用获得许可的 [!DNL Insight]. 有关使用AccessGroups控制对服务器的访问的其他信息，请参见 [配置访问控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**更新访问控制文件**

1. 导航到 [!DNL Access Control] 文件夹（位于您安装的目录中） [!DNL Insight Server].

   示例：[!DNL C:\Adobe\Server\Access Control]

1. 打开 [!DNL Access Control.cfg] 文件格式的文件，例如记事本。
1. 在Administrators AccessGroup中找到CN条目，并用标识 [!DNL Insight] 用于初始设置和管理 [!DNL Insight Server]. 以下文件片段说明了在中插入公共名称的位置 [!DNL Access Control.cfg] 文件。

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

   如果您使用基于凭据的身份验证，则有一些额外的条目可用于配置。 这些条目包括：

   * O（组织ID）：此条目表示组织的ID。 例如：`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。此ID可在Admin Console中找到。
   * PLC — 此条目允许访问为特定产品配置配置的用户。 它可以在格式中使用 `Organization_Id-PLC`. 例如：`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。为使用PLC进行Data Workbench而配置的用户 `DataworkbenchAdminUsers` 将获得对其服务器的访问权限。
   * 电子邮件 — 此条目允许访问任何个人用户。 其值应为已设置用户的电子邮件地址。 例如：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 这些条目区分大小写。 您必须确保为O、PLC和Email指定的值与Admin Console中显示的值完全相同。
   >    * 键入与证书上显示的名称完全相同的公用名。
   >    * 请勿使用Tab键在中生成空格 [!DNL Access Control.cfg] 文件(或在Adobe组件的任何其他配置文件中)。 仅使用空格创建空格。 制表符会阻止系统正确读取文件。


1. 保存并关闭该文件。
