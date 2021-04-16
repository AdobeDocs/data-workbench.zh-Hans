---
description: 要使报表门户能够写入包含用户身份验证所需信息的数据库，必须为数据库设置适当的权限。
title: 设置数据库的权限
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# 设置数据库的权限{#set-permissions-for-the-database}

要使报表门户能够写入包含用户身份验证所需信息的数据库，必须为数据库设置适当的权限。

1. 在运行IIS的计算机上，导航到\*PortalName*\data\users.mdb。
1. 右键单击&#x200B;**[!UICONTROL users.mdb]**&#x200B;文件，然后选择&#x200B;**[!UICONTROL Properties]**。
1. 在[!DNL Security]选项卡的“组”或“用户名”中，单击&#x200B;**[!UICONTROL Users]**。
1. 在[!DNL Permission for User]的“写入”行中，选择&#x200B;**[!UICONTROL Allow]**。
1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;并关闭[!DNL Properties]对话框。
