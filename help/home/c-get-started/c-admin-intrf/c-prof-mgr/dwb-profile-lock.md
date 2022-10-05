---
description: “配置文件管理器”中应用的 Internal.cfg 文件可防止用户通过配置文件、维度、报表、工作区、量度和过滤器管理器对您的自定义配置文件进行更改。
title: 锁定工作站中的配置文件
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 90%

---

# 锁定工作站中的配置文件{#locking-profiles-in-the-workstation}

{{eol}}

“配置文件管理器”中应用的 Internal.cfg 文件可防止用户通过配置文件、维度、报表、工作区、量度和过滤器管理器对您的自定义配置文件进行更改。

使用管理器时，您可以防止配置文件遭到修改和覆盖，具体方法是：在配置文件管理器中，将 **[!DNL Internal.cfg]** 文件保存到您的自定义配置文件中。该配置文件可以防止用户在管理器（通过&#x200B;**管理员** > **配置文件**&#x200B;菜单访问）中执行操作时覆盖多个文件。

**锁定配置文件管理器中的配置文件**

1. 在工作区中，右键单击&#x200B;**管理员** > **配置文件管理器**。

1. 在 **配置文件管理器**，右键单击 **[!DNL Context > Internal.cfg]** 和 **制作本地副本**.

1. 在中右键单击复选标记 **用户** 列并保存到 `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**注意：**&#x200B;将 **[!DNL Internal.cfg]** 文件保存到“配置文件管理器”中的自定义配置文件时，只能阻止管理器对配置文件进行更改。您仍可以使用&#x200B;**保存到服务器**&#x200B;命令，通过工作台将工作区保存到服务器中。
