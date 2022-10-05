---
description: 在功能板可以操作之前，必须允许它访问SQL Server。
title: 配置 SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# 配置 SQL Server{#configuring-the-sql-server}

{{eol}}

在功能板可以操作之前，必须允许它访问SQL Server。

1. 以管理员身份打开SQL Management Studio。
1. 通过右键单击添加新登录 **[!UICONTROL Logins]** 选择 **[!UICONTROL New Login]**.
1. 输入完整的应用程序池标识名称。

   默认情况下，应用程序池标识以应用程序池的名称命名。 如果您选择 `dashboard`，则将命名标识 `IIS AppPool\dashboard`. 1.选择 **[!UICONTROL Server Roles]** 并检查 **[!UICONTROL dbcreator]** 角色。
1. 单击 **[!UICONTROL OK]** 以添加新用户。
