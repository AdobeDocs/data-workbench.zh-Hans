---
description: 用户在访问报告门户时必须具有有效的帐户并提供帐户名称和密码。
title: 定义其他帐户
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# 定义其他帐户

用户在访问报告门户时必须具有有效的帐户并提供帐户名称和密码。

默认情况下，在[!DNL Report Portal]中启用用户身份验证。

[!DNL Report Portal]的有效帐户列表将保留在数据库文件[!DNL portal.mdb]中。 [!DNL Report Portal] 安装时安装了一个具有管理权限的帐户：

* 帐户名称：测试
* 密码：用户

>[!NOTE]
>
>出于安全原因，Adobe建议您在安装[!DNL Report Portal]后更改此帐户的口令。

要向[!DNL Report Portal]添加用户帐户或更改与现有帐户相关的信息，请使用[!DNL Report Portal]用户界面上的[!DNL Admin]选项卡。

每次添加新帐户或编辑现有帐户时，都会按照\*PortalName*\PortalASP文件夹中[!DNL email.asp]文件中的指定发送确认电子邮件。 有关详细信息，请参阅[编辑Email.asp文件](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)。

有关添加其他用户的步骤，请参阅[使用帐户](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)。

>[!NOTE]
>
>或者，您可以禁用用户身份验证并允许对[!DNL Report Portal]进行匿名访问。 有关执行此操作的步骤，请参阅[编辑会话配置文件](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)中有关Session(&quot;In&quot;)参数的信息。
