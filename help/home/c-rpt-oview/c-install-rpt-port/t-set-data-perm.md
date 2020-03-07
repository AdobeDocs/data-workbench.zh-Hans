---
description: 要使报告门户能够写入包含用户身份验证所需信息的数据库，必须为数据库设置适当的权限。
solution: Analytics
title: 设置数据库的权限
topic: Data workbench
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 设置数据库的权限{#set-permissions-for-the-database}

要使报告门户能够写入包含用户身份验证所需信息的数据库，必须为数据库设置适当的权限。

1. 在运行IIS的计算机上，导航到\*PortalName*\data\users.mdb。
1. 右键单击文 **[!UICONTROL users.mdb]** 件并选择 **[!UICONTROL Properties]**。
1. 在选项 [!DNL Security] 卡的组或用户名中，单击 **[!UICONTROL Users]**。
1. 在 [!DNL Permission for User]“写入”行中，选择 **[!UICONTROL Allow]**。
1. 单击 **[!UICONTROL OK]** 并关闭对 [!DNL Properties] 话框。
