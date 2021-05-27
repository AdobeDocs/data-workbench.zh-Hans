---
description: 功能板产品需要ClientCare提供的Adobe。
title: 添加功能板许可证密钥
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# 添加功能板许可证密钥{#add-dashboard-license-key}

功能板产品需要ClientCare提供的Adobe。

1. 以管理员身份打开&#x200B;**[!UICONTROL SQL Management Studio]**。
1. 打开由功能板创建的数据库（例如，thinclientdb）。
1. 右键单击&#x200B;**[!UICONTROL Configuration]**&#x200B;表，然后单击&#x200B;**[!UICONTROL Edit Top 200 Rows]**。
1. 找到&#x200B;**[!UICONTROL licenseKey]**&#x200B;字段，并在&#x200B;**[!UICONTROL Value]**&#x200B;列中输入AdobeClientCare提供的键。
1. 在&#x200B;**[!UICONTROL IIS Manager Console]**&#x200B;中重新启动&#x200B;**[!UICONTROL Application Pool]**。
