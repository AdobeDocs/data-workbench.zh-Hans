---
description: 编辑现有用户帐户的步骤。
title: 编辑现有用户
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# 编辑现有用户{#editing-existing-users}

编辑现有用户帐户的步骤。

1. 在[!DNL Report Portal]中，单击&#x200B;**[!UICONTROL Admin]**&#x200B;选项卡。 将显示[!DNL Admin]页。

   ![](assets/report_admintag2.png)

1. 单击表示要编辑的帐户名称的第一个字母的字母。 例如，如果要编辑帐户“Marketing”，可单击字母“M”。

   将显示以该字母开头的帐户名列表。

1. 选择要编辑的帐户名，然后单击&#x200B;**[!UICONTROL select]**&#x200B;按钮。 将显示[!DNL Edit Account Info]页。

   ![步骤信息](assets/rptPort_scrn_AdminTab_editUser.png)

1. 仅更改此页面上需要更新的字段。 下表提供了这些字段的说明：

   | 在此字段中。.. | 在“管理工具”中指定分类的 . . . |
   |---|---|
   | 电子邮件 | 用户的电子邮件地址。 |
   | 旧密码 | 当前密码，在编辑管理员帐户或重置非管理员帐户的密码时需要继续。 |
   | 新密码 | 用户登录[!DNL Report Portal]时必须提供的新密码。 |
   | 确认密码 | 用户登录[!DNL Report Portal]时必须提供的新密码。 |
   | 用户档案访问 | 允许此用户访问的用户档案（例如，ProductSales）。 要允许访问多个用户档案，请用逗号分隔这些名称。 如果允许用户访问与[!DNL Report Portal]关联的所有用户档案，请键入“ALL”。 |
   | 选项卡访问 | 允许此用户访问的选项卡（例如[!DNL Admin]）。 要允许访问多个选项卡，请用逗号分隔这些名称。 如果允许用户访问[!DNL Report Portal]中的所有选项卡，请键入“ALL”。 此字段与帐户类型字段一起用于定义组访问权限。 |
   | 帐户类型 | 此帐户是针对个人还是群组。 单个帐户使用户能够重置其密码，而组不会重置。 管理员是唯一能够重置组帐户密码的人。 |
   | status | 此帐户是活动帐户还是非活动帐户。 默认值为活动值。 要取消激活用户帐户，请选择&#x200B;**[!UICONTROL inactive]**。 |
   | admin | 是否允许此用户创建、更新和删除用户帐户，以及编辑与每个报表关联的备注。 默认值设置为 false。要使其成为管理员用户，请选择true。 |
   | 过期日期 | 允许此用户使用[!DNL Report Portal]的日期，以MM/DD/YYYY格式显示。 |

1. 单击 **[!UICONTROL update]**。
