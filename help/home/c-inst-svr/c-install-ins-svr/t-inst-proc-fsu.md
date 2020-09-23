---
description: 安装Insight Server FSU并将其配置为用于管理用途的说明与安装和配置Insight Server DPU的说明非常相似。
solution: Analytics
title: Insight Server FSU 的安装过程
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---


# Insight Server FSU 的安装过程{#installation-procedures-for-an-insight-server-fsu}

安装Insight Server FSU并将其配置为用于管理用途的说明与安装和配置Insight Server DPU的说明非常相似。

对于 *Windows 2012服务器中的* MS System Center端点保护，需要将这些可执行文件添加到“已排 **除的进程”:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

要安装和配置FSU, [!DNL Insight Server] 您必须完成以下任务:

1. 安装 [!DNL Insight Server] 项目文件。
1. 安装数 [!DNL Insight Server] 字证书。
1. 检查文件中的端口 [!DNL Communications.cfg] 设置。
1. 修改文 [!DNL Access Control.cfg] 件，以允许从进行管理 [!DNL the Server] 访问 [!DNL the Client]。
1. 修改文 [!DNL server.address] 件以定义服务器的网络位置。
1. 按说明设置Windows内存使用参数。
1. 按照 [!DNL Insight Server] 说明注册为Windows服务。

   有关为FSU配置数据源、权限和通信的说 [!DNL Insight Server] 明，请参阅 *Dataset Configuration Guide*。

