---
description: 在功能板可以操作之前，您必须允许它访问SQL Server。
solution: Analytics
title: 配置SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置SQL Server{#configuring-the-sql-server}

在功能板可以操作之前，您必须允许它访问SQL Server。

1. 以管理员身份打开SQL Management Studio。
1. 通过右键单击并选择来添加新 **[!UICONTROL Logins]** 登录名 **[!UICONTROL New Login]**。
1. 输入完整的应用程序池标识名称。

   默认情况下，应用程序池标识以应用程序池命名。 如果您选 `dashboard`择，则将命名标识 `IIS AppPool\dashboard`。 1.选择 **[!UICONTROL Server Roles]** 并检查角 **[!UICONTROL dbcreator]** 色。
1. Click **[!UICONTROL OK]** to add the new user.
