---
description: 最后一步是首次运行仪表板以允许其初始化。
title: 初始化功能板
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# 初始化功能板{#initializing-the-dashboard}

最后一步是首次运行仪表板以允许其初始化。

1. 打开Web浏览器并输入新部署站点的URL(例如，http://localhost/dashboard)。
1. 首次连接将设置数据库表，因此可能会遇到稍微的延迟。
1. 初始登录凭据有：

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 首次登录时，转到&#x200B;**[!UICONTROL User]** > **[!UICONTROL Account Settings]**&#x200B;并选择&#x200B;**[!UICONTROL Change Password]**&#x200B;以更改管理员密码。

仪表板安装现已完成。 如果尚未配置，请使用本指南的准备Data Workbench部分中详细说明来配置与Data Workbench Server的通信以及管理用户和组。

>[!NOTE]
>
>仪表板错误和审核日志可在安装路径的[!DNL logs]目录中找到。

>[!NOTE]
>
>如果需要将应用程序池标识更改为其他帐户，请确保授予对数据库的访问权，并授予对安装路径中[!DNL logs]文件夹的标识读/写访问权限。

>[!NOTE]
>
>如果您曾经需要更改数据库的连接字符串，只需使用&#x200B;**[!UICONTROL IIS Management Console]**&#x200B;编辑值。
