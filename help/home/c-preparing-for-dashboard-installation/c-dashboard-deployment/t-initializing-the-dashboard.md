---
description: 最后一步是首次运行功能板，以允许其初始化。
solution: Analytics
title: 初始化功能板
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 初始化功能板{#initializing-the-dashboard}

最后一步是首次运行功能板，以允许其初始化。

1. 打开Web浏览器并输入新部署站点的URL(例如，http://localhost/dashboard)。
1. 首次连接将设置数据库表，因此您可能会遇到稍微的延迟。
1. 初始登录凭据有：

* **[!UICONTROL Username]**: admin
* **[!UICONTROL Password]**: password

1. 第一次登录时，转到 **[!UICONTROL User]** >并 **[!UICONTROL Account Settings]** 选择 **[!UICONTROL Change Password]** 以更改管理员密码。
>功能板安装现已完成。 如果尚未安装，请使用>中详细说明
><!-->
>准备数据工作>
>-->
>本指南的下一节将配置与Data Workbench Server的通信以及管理用户和组。 >
>>[!NOTE]
>>
>>功能板错误和审核日志可在安装路径 [!DNL logs] 的目录中找到。
>[!NOTE]
如果需要将应用程序池标识更改为其他帐户，请确保授予对数据库的访问权，并授予对安装路径中文件夹的标识读／写 [!DNL logs] 访问权限。
>[!NOTE]
如果您曾经需要更改数据库的连接字符串，只需使用编辑该值即可 **[!UICONTROL IIS Management Console]**。
>
>
>
