---
description: 在功能板可以操作之前，必须允许它访问SQL Server。
title: 配置 SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# 配置 SQL Server{#configuring-the-sql-server}

在功能板可以操作之前，必须允许它访问SQL Server。

1. 以管理员身份打开SQL Management Studio。
1. 右键单击&#x200B;**[!UICONTROL Logins]**&#x200B;并选择&#x200B;**[!UICONTROL New Login]**&#x200B;以添加新登录。
1. 输入完整的应用程序池标识名称。

   默认情况下，应用程序池标识以应用程序池的名称命名。 如果选择`dashboard`，则该标识将被命名为`IIS AppPool\dashboard`。 1.选择&#x200B;**[!UICONTROL Server Roles]**&#x200B;并检查&#x200B;**[!UICONTROL dbcreator]**&#x200B;角色。
1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;以添加新用户。
