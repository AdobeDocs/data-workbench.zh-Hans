---
description: 添加新帐户的步骤。
solution: Analytics
title: 添加新帐户
topic: Data workbench
uuid: 32081bc3-9050-42a2-95ad-85e7736fe5c4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 添加新帐户{#adding-new-accounts}

添加新帐户的步骤。

1. 在中， [!DNL Report Portal]单击该选 **[!UICONTROL Admin]** 项卡。 将显 [!DNL Admin] 示页面。

   ![](assets/report_admintag2.png)

1. 在页面的右侧，单击 **[!UICONTROL new account]**。 将显 [!DNL Create New Account] 示页面。

   ![步骤信息](assets/rptPort_scrn_AdminTab_createUser.png)

1. 按照下表中的指示完成此页上的所有字段：

   | 在此字段中。.. | 在“管理工具”中指定分类的 . . . |
   |---|---|
   | 帐户名 | 用户登录时必须提供的帐户名称 [!DNL Report Portal]。 |
   | 电子邮件 | 用户或用户组的电子邮件地址。 |
   | password | 用户登录时必须提供的口令 [!DNL Report Portal]。 |
   | 确认密码 | 用户登录时必须提供的口令 [!DNL Report Portal]。 |
   | 个人资料访问 | 允许此用户访问的配置文件（例如，ProductSales）。 要允许访问多个配置文件，请用逗号分隔这些名称。 如果允许用户访问与之关联的所有配置文件， [!DNL Report Portal]请键入“ALL”。 |
   | 选项卡访问权 | 允许此用户访问的选项卡(例如， [!DNL Admin])。 要允许访问多个选项卡，请用逗号分隔这些名称。 如果允许用户访问中的所有选项卡， [!DNL Report Portal]请键入“ALL”。此字段与帐户类型字段一起用于定义组访问权限。 |
   | 帐户类型 | 无论此帐户是针对个人还是针对组。 单个帐户使用户能够重置其密码，而组则不能。 管理员是唯一能够重置组帐户密码的人员。 |
   | status | 此帐户是处于活动状态还是非活动状态。 默认值为活动值。 要取消激活用户帐户，请选择“非活动”。 |
   | admin | 是否允许此用户创建、更新和删除用户帐户以及编辑与每个报告关联的备注。 默认值设置为 false。要使其成为管理员用户，请选择true。 |
   | 到期日 | 日期，以MM/DD/YYYY格式显示，直到允许此用户使用 [!DNL Report Portal]。 |

1. 单击 **[!UICONTROL insert]**.