---
description: 最后一步是首次运行功能板以允许其初始化。
title: 初始化仪表板
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# 初始化仪表板{#initializing-the-dashboard}

{{eol}}

最后一步是首次运行功能板以允许其初始化。

1. 打开Web浏览器并输入新部署站点的URL(例如，https://localhost/dashboard)。
1. 首次连接将设置数据库表，因此可能会遇到轻微延迟。
1. 初始登录凭据包括：

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 首次登录时，转到 **[!UICONTROL User]** > **[!UICONTROL Account Settings]** 选择 **[!UICONTROL Change Password]** 更改管理员密码。

功能板安装现已完成。 如果您尚未集成，请按照本指南的准备Data Workbench部分中详细的说明配置您与Data Workbench Server的通信并管理用户和组。

>[!NOTE]
>
>在 [!DNL logs] 目录。

>[!NOTE]
>
>如果需要将应用程序池标识更改为其他帐户，请确保授予对数据库的访问权限，并授予对 [!DNL logs] 文件夹。

>[!NOTE]
>
>如果需要更改数据库的连接字符串，只需使用 **[!UICONTROL IIS Management Console]**.
