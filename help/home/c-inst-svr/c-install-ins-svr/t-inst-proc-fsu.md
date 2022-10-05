---
description: 安装Insight Server FSU并将其配置为管理用途的说明与安装和配置Insight Server DPU的说明非常相似。
title: Insight Server FSU 的安装过程
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Insight Server FSU 的安装过程{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

安装Insight Server FSU并将其配置为管理用途的说明与安装和配置Insight Server DPU的说明非常相似。

对于 *MS System Center Endpoint Protection* 在Windows 2012服务器中，需要将这些可执行文件添加到 **排除的流程：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

安装和配置 [!DNL Insight Server] FSU，您必须完成以下任务：

1. 安装 [!DNL Insight Server] 程序文件。
1. 安装 [!DNL Insight Server] 数字证书。
1. 检查 [!DNL Communications.cfg] 文件。
1. 修改 [!DNL Access Control.cfg] 允许管理访问权限的文件 [!DNL the Server] 从 [!DNL the Client].
1. 修改 [!DNL server.address] 文件来定义服务器的网络位置。
1. 按照说明设置Windows内存使用参数。
1. 注册 [!DNL Insight Server] 作为Windows服务（如所述）。

   有关为 [!DNL Insight Server] FSU，看 *数据集配置指南*.
