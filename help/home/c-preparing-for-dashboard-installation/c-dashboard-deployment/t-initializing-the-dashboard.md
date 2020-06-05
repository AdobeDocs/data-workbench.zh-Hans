---
description: 最后一步是首次运行仪表板，以允许其初始化。
solution: Analytics
title: 初始化仪表板
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---


# 初始化仪表板{#initializing-the-dashboard}

最后一步是首次运行仪表板，以允许其初始化。

1. 打开Web浏览器并输入新部署站点的URL(例如，http://localhost/dashboard)。
1. 首次连接将设置数据库表，因此可能会有轻微延迟。
1. 初始登录凭据包括：

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 首次登录时，转到> **[!UICONTROL User]** 并 **[!UICONTROL Account Settings]** 选择 **[!UICONTROL Change Password]** 以更改管理员密码。

仪表板安装现已完成。 如果尚未配置，请使用本指南的“准备数据工作台”部分中详细说明来配置与Data Workbench Server的通信以及管理用户和组。

>[!NOTE]
>
>仪表板错误和审计日志可在安装路径 [!DNL logs] 的目录中找到。

>[!NOTE]
>
>如果需要将应用程序池标识更改为其他帐户，请确保授予对数据库的访问权，并授予对安装路径中文件夹的标 [!DNL logs] 识读／写访问权限。

>[!NOTE]
>
>如果您曾经需要更改数据库的连接字符串，只需使用编辑值 **[!UICONTROL IIS Management Console]**。
