---
description: 用户在访问报告门户时必须具有有效的帐户并提供帐户名称和密码。
solution: Analytics
title: 定义其他帐户
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定义其他帐户{#define-additional-accounts}

用户在访问报告门户时必须具有有效的帐户并提供帐户名称和密码。

默认情况下，在中启用用户身份验证 [!DNL Report Portal]。

数据库文件中将保 [!DNL Report Portal] 留有效帐户的列表 [!DNL portal.mdb]。 [!DNL Report Portal] 使用一个帐户安装，并具有管理权限：

* 帐户名称：测试
* 密码：用户

>[!NOTE]
>
>出于安全原因，Adobe建议您在安装后更改此帐户的口令 [!DNL Report Portal]。

要向现有帐户添加用 [!DNL Report Portal] 户帐户或更改与现有帐户相关的信息，请使用用 [!DNL Admin] 户界面上的 [!DNL Report Portal] 选项卡。

每次添加新帐户或编辑现有帐户时，都会按照\*PortalName*\PortalASP文件夹中 [!DNL email.asp] 的文件中的指定发送确认电子邮件。 有关详细信息，请 [参阅编辑Email.asp文件](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)。

有关添加其他用户的步骤，请参阅 [使用帐户](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)。

>[!NOTE]
>
>或者，您也可以禁用用户身份验证并允许匿名访问 [!DNL Report Portal]。 要执行此操作的步骤，请参阅编辑会话配置文件中有关Session(&quot;In&quot;) [参数的信息](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)。

