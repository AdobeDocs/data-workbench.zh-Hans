---
description: 编辑现有用户帐户的步骤。
title: 编辑现有用户
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# 编辑现有用户{#editing-existing-users}

{{eol}}

编辑现有用户帐户的步骤。

1. 在 [!DNL Report Portal]，请单击 **[!UICONTROL Admin]** 选项卡。 的 [!DNL Admin] 页面。

   ![](assets/report_admintag2.png)

1. 单击表示要编辑的帐户名称的第一个字母的字母。 例如，如果要编辑帐户“营销”，可单击字母“M”。

   将显示以该信件开头的帐户名称列表。

1. 选择要编辑的帐户名称，然后单击 **[!UICONTROL select]** 按钮。 的 [!DNL Edit Account Info] 页面。

   ![步骤信息](assets/rptPort_scrn_AdminTab_editUser.png)

1. 仅更改此页面上需要更新的字段。 下表提供了这些字段的说明：

   | 在此字段中。.. | 在“管理工具”中指定分类的 . . . |
   |---|---|
   | 电子邮件 | 用户的电子邮件地址。 |
   | 旧密码 | 当前密码，在编辑管理员帐户或重置非管理员帐户的密码时需要继续该密码。 |
   | 新密码 | 登录时用户必须提供的新密码 [!DNL Report Portal]. |
   | 确认密码 | 登录时用户必须提供的新密码 [!DNL Report Portal]. |
   | 配置文件访问 | 允许此用户访问的配置文件（例如，ProductSales）。 要允许访问多个配置文件，请使用逗号分隔各个名称。 如果允许用户访问与关联的所有用户档案 [!DNL Report Portal]，键入“ALL”。 |
   | 选项卡访问权限 | 允许此用户访问的选项卡(例如， [!DNL Admin])。 要允许访问多个选项卡，请用逗号分隔各个名称。 如果允许用户访问 [!DNL Report Portal]，键入“ALL”。 此字段与帐户类型字段一起用于定义组访问权限。 |
   | 帐户类型 | 此帐户是针对个人还是群组。 单个帐户允许用户重置密码，而组则不会重置密码。 管理员是唯一能够重置群组帐户密码的人员。 |
   | status | 此帐户是活动帐户还是不活动帐户。 默认值为活动值。 要停用用户帐户，请选择 **[!UICONTROL inactive]**. |
   | admin | 是否允许此用户创建、更新和删除用户帐户，以及编辑与每个报表关联的注释。 默认值设置为 false。要将此用户设为管理员用户，请选择true。 |
   | 过期日期 | 日期（YYYY/MM/DD格式），在该日期之前，允许此用户使用 [!DNL Report Portal]. |

1. 单击 **[!UICONTROL update]**。
