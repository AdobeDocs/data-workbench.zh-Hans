---
description: 用户在访问报表门户时必须拥有有效的帐户并提供帐户名称和密码。
title: 定义其他帐户
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# 定义其他帐户

用户在访问报表门户时必须拥有有效的帐户并提供帐户名称和密码。

默认情况下，在[!DNL Report Portal]中启用用户身份验证。

[!DNL Report Portal]的有效帐户列表在数据库文件[!DNL portal.mdb]中进行维护。 [!DNL Report Portal] 已安装一个具有管理权限的帐户：

* 帐户名称：测试
* 密码：用户

>[!NOTE]
>
>出于安全考虑，Adobe建议您在安装[!DNL Report Portal]后更改此帐户的密码。

要向[!DNL Report Portal]添加用户帐户或更改与现有帐户相关的信息，请使用[!DNL Report Portal]用户界面上的[!DNL Admin]选项卡。

每次添加新帐户或编辑现有帐户时，都会按\*PortalName*\PortalASP文件夹[!DNL email.asp]文件中指定的方式发送确认电子邮件。 有关更多信息，请参阅[编辑Email.asp文件](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)。

有关添加其他用户的步骤，请参阅[使用帐户](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)。

>[!NOTE]
>
>或者，您也可以禁用用户身份验证并允许匿名访问[!DNL Report Portal]。 要执行此操作的步骤，请参阅[Edit the Session Configuration File](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)中有关Session(&quot;In&quot;)参数的信息。
