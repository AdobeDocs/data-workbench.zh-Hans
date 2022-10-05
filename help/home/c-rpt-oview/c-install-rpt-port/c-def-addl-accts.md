---
description: 用户在访问报表门户时必须拥有有效的帐户并提供帐户名称和密码。
title: 定义其他帐户
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# 定义其他帐户

{{eol}}

用户在访问报表门户时必须拥有有效的帐户并提供帐户名称和密码。

默认情况下，在 [!DNL Report Portal].

的有效帐户列表 [!DNL Report Portal] 在数据库文件中维护， [!DNL portal.mdb]. [!DNL Report Portal] 已安装一个具有管理权限的帐户：

* 帐户名称：测试
* 密码：用户

>[!NOTE]
>
>出于安全考虑，Adobe建议您在安装后更改此帐户的密码 [!DNL Report Portal].

将用户帐户添加到 [!DNL Report Portal] 或更改与现有帐户相关的信息，则使用 [!DNL Admin] 选项卡 [!DNL Report Portal] 用户界面。

每次您添加新帐户或编辑现有帐户时，系统都会按照 [!DNL email.asp] 文件。 有关更多信息，请参阅 [编辑Email.asp文件](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

有关添加其他用户的步骤，请参阅 [使用帐户](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>或者，您也可以禁用用户身份验证并允许匿名访问 [!DNL Report Portal]. 有关执行此操作的步骤，请参阅 [编辑会话配置文件](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
