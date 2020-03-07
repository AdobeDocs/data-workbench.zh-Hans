---
description: 安装Insight Server FSU并将其配置为用于管理用途的说明与安装和配置Insight Server DPU的说明非常相似。
solution: Insight
title: Insight Server FSU的安装过程
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Server FSU的安装过程{#installation-procedures-for-an-insight-server-fsu}

安装Insight Server FSU并将其配置为用于管理用途的说明与安装和配置Insight Server DPU的说明非常相似。

对于 *Windows 2012 Server中的MS System Center Endpoint Protection* ，这些可执行文件需要添加到“已排除的进 **程”中：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

要安装和配置 [!DNL Insight Server] FSU，您必须完成以下任务：

1. 安装程 [!DNL Insight Server] 序文件。
1. 安装数 [!DNL Insight Server] 字证书。
1. 检查文件中的端口 [!DNL Communications.cfg] 设置。
1. 修改文 [!DNL Access Control.cfg] 件，以允许管理访问 [!DNL the Server] 自 [!DNL the Client]。
1. 修改文 [!DNL server.address] 件以定义服务器的网络位置。
1. 按说明设置Windows内存使用参数。
1. 按照 [!DNL Insight Server] 说明注册为Windows服务。

   有关为FSU配置数据源、权限和通信的说明，请参 [!DNL Insight Server] 阅《数据集配 *置指南》*。

