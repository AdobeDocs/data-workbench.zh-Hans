---
description: 功能板产品需要ClientCare提供的Adobe。
title: 添加仪表板许可证密钥
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# 添加仪表板许可证密钥{#add-dashboard-license-key}

{{eol}}

功能板产品需要ClientCare提供的Adobe。

1. 打开 **[!UICONTROL SQL Management Studio]** 作为管理员。
1. 打开由功能板创建的数据库（例如，thinclientdb）。
1. 右键单击 **[!UICONTROL Configuration]** 表格和单击 **[!UICONTROL Edit Top 200 Rows]**.
1. 查找 **[!UICONTROL licenseKey]** 字段，并在中输入AdobeClientCare提供的键 **[!UICONTROL Value]** 列。
1. 重新启动 **[!UICONTROL Application Pool]** 在 **[!UICONTROL IIS Manager Console]**.
