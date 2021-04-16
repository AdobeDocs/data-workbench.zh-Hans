---
description: 安装Insight Server FSU并将其配置为管理用途的说明与安装和配置Insight Server DPU的说明非常相似。
title: Insight Server FSU 的安装过程
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Insight Server FSU 的安装过程{#installation-procedures-for-an-insight-server-fsu}

安装Insight Server FSU并将其配置为管理用途的说明与安装和配置Insight Server DPU的说明非常相似。

对于Windows 2012 Server中的&#x200B;*MS System Center Endpoint Protection*，需要将这些可执行文件添加到&#x200B;**排除的进程：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

要安装和配置[!DNL Insight Server] FSU，必须完成以下任务:

1. 安装[!DNL Insight Server]项目文件。
1. 安装[!DNL Insight Server]数字证书。
1. 检查[!DNL Communications.cfg]文件中的端口设置。
1. 修改[!DNL Access Control.cfg]文件，以允许从[!DNL the Client]对[!DNL the Server]进行管理访问。
1. 修改[!DNL server.address]文件以定义服务器的网络位置。
1. 按说明设置Windows内存使用参数。
1. 按照说明将[!DNL Insight Server]注册为Windows服务。

   有关为[!DNL Insight Server] FSU配置数据源、权限和通信的说明，请参阅&#x200B;*数据集配置指南*。
