---
description: 使用工作站管理您的Data Workbench用户。
title: 用户自供应
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 用户自供应{#self-provisioning-of-users}

使用工作站管理您的Data Workbench用户。

您可以通过从Adobe设置所需的证书，使用工作站连接到Data Workbench Server。 此证书有助于进行SSL通信和授权以使用许可的资源和功能。 在基于证书的身份验证中，您需要获取并设置多个证书以在多台计算机上使用工作站。 此外，用户配置和授权由Adobe管理，您必须与Adobe联系以获取新证书或证书撤销。

从DWB 6.7开始，工作站支持通过用户名和密码进行用户身份验证。

虽然基于证书的身份验证／授权仍适用于您的设置，但强烈建议迁移到较新的基于凭据的身份验证。 在较新的方法中，您的工作站用户通过Adobe身份管理系统(IMS)验证自己的身份。 在使用工作站之前，组织管理员需要通过 [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) ，授予他们访问这些功能的权限。

新的身份验证和用户供应模型有助于：

* 通过Admin Console自配置用户和用户组。 您不必联系Adobe即可添加、删除或修改用户的许可授权。
* 使用凭据登录，从多台计算机访问工作站而不会丢失配置状态。 注销时将删除本地缓存，关闭当前配置文件，并且配置文件将变为活动状态。

## 入门指南

在开始之前，请与Adobe联系，以在Admin Console中添加您的组织。 根据您购买的服务，Adobe将为您提供组织。 例如，组织可以访问Attribution服务或Beta版本，或同时访问这两者。 配置组织后，组织管理员可以添加用户和用户组。 有关更 [多信息，请参阅管理Experience Cloud中的Experience](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) Cloud用户和产品。 组织管理员还可以根据不同用户的角色为其配置使用限制。 例如，非预发行版用户无需访问测试版内部版本。

通过Admin Console添加到此组织的每个已配置用户都将有权使用数据工作台。 子服务只能针对每个用户启用或禁用，具体取决于其产品访问权限。 当用户从证书升级到IMS时，所有本地数据都将被复制到新的IMS用户目录。

>[!NOTE]
>
>除非刷新访问令牌，否则会话在服务器上持续6小时，在客户端持续23小时。 刷新令牌后，您无需再次登录即可使用客户端。

在授予任何用户访问权限之前，管理员需要在管理控制台中至少创建一个产品级别配置。

可以添加布 **尔标志“使用IMS** ”，以 [!DNL Insight.cfg] 回退到证书模式。 有关为IMS用户配置访问控制的信息，请参 [阅更新访问控制文件](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html)。

## 冲突解决

当用户登录到多台计算机时，如果同一配置文件上具有相同IMS帐户，并且在其中一台计算机上处于脱机模式，则可能会显示表单并弹出窗口通知您。 `.conflict` 当内容与任何文件（工作区、尺寸、过滤器等）存在差异时，会发生这种情况已同步到服务器和客户端上[!DNL User\Profile\]中的两台计算机上。 将在文件中创建一 `.conflict` 个备份，不会丢失任何数据。 中的布尔标 [!DNL Insight.cfg] 志允许您禁用此冲突弹出窗口。

旗标：冲突通知

这适用于工作区、度量、维度等。 中。
