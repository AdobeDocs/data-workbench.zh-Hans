---
description: 要使报表门户能够写入包含用户身份验证所需信息的数据库，必须为数据库设置适当的权限。
title: 设置数据库的权限
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# 设置数据库的权限{#set-permissions-for-the-database}

{{eol}}

要使报表门户能够写入包含用户身份验证所需信息的数据库，必须为数据库设置适当的权限。

1. 在运行IIS的计算机上，导航到\*PortalName*\data\users.mdb。
1. 右键单击 **[!UICONTROL users.mdb]** 文件，选择 **[!UICONTROL Properties]**.
1. 在 [!DNL Security] 选项卡，在组或用户名中，单击 **[!UICONTROL Users]**.
1. 在 [!DNL Permission for User]，在“写入”行中，选择 **[!UICONTROL Allow]**.
1. 单击 **[!UICONTROL OK]** 然后关闭 [!DNL Properties] 对话框。
