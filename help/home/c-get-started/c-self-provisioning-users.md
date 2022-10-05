---
description: 使用工作站管理您的Data Workbench用户。
title: 自动配置用户
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# 自动配置用户{#self-provisioning-of-users}

{{eol}}

使用工作站管理您的Data Workbench用户。

您可以通过从Data Workbench中设置所需的证书来使用工作站连接到Adobe服务器。 此证书有助于进行SSL通信和授权以使用许可的资源和功能。 在基于证书的身份验证中，您需要获取并设置多个证书，以便在多台计算机上使用工作站。 此外，用户配置和授权由Adobe管理，您必须联系Adobe以获取新证书或证书吊销。

从DWB 6.7开始，工作站支持通过用户名和密码进行用户身份验证。

虽然基于证书的身份验证/授权仍适用于您的设置，但强烈建议迁移到较新的基于凭据的身份验证。 在较新的方法中，您的工作站用户通过AdobeIdentity Management系统(IMS)来验证自己。 在使用工作站之前，需要先通过 [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 由组织的管理员进行。

新的身份验证和用户配置模型有助于：

* 通过Admin Console自动配置用户和组。 您无需联系Adobe即可添加、删除或修改用户的许可证权限。
* 使用凭据登录，从多台计算机访问工作站，而不会丢失配置状态。 注销时将删除本地缓存，关闭当前配置文件，并且“配置”配置文件会变为活动状态。

## 快速入门

在开始之前，请联系Adobe以在Admin Console中添加您的组织。 根据您购买的服务，Adobe将为您配置组织。 例如，组织可以访问归因服务或测试版内部版本，或者同时访问这两者。 配置组织后，组织管理员可以添加用户和组。 请参阅 [管理Experience Cloud用户和产品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) Experience Cloud。 组织管理员还可以根据不同用户的角色为其配置使用限制。 例如，非预发行用户无需访问测试版内部版本。

通过Admin Console添加到此组织的每个已配置用户都将有权使用Data Workbench。 只能为每个用户启用或禁用子服务，具体取决于其产品访问权限。 当用户从证书升级到IMS时，所有本地数据都将复制到新的IMS用户目录。

>[!NOTE]
>
>会话在服务器上持续6小时，在客户端持续23小时，除非刷新访问令牌。 刷新令牌后，您可以使用客户端，而无需再次登录。

在授予任何用户访问权限之前，需要管理员在Admin Console中创建至少一个产品级配置。

布尔标记 **使用IMS** 可添加到 [!DNL Insight.cfg] 回退到证书模式。 有关为IMS用户配置访问控制的信息，请参阅 [更新访问控制文件](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## 冲突解决

当用户在同一配置文件上使用相同的IMS帐户登录到多台计算机，并且在其中一台计算机上处于脱机模式时， `.conflict` 可以窗体，弹出窗口会通知您。 当内容与任何文件（工作区、维度、过滤器等）存在差异时，会发生这种情况 在两台计算机上同步 [!DNL User\Profile\] 在服务器和客户端上。 将在 `.conflict` 文件，并且不会丢失任何数据。 中的布尔标记 [!DNL Insight.cfg] 允许您禁用此冲突弹出窗口。

标记：冲突通知

这适用于工作区、量度、维度等。 （在用户文件夹中）。
