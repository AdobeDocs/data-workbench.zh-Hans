---
description: 从5.4安装升级Data Workbench6.1的服务器组件。
title: DWB服务器升级5.4到5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 39%

---

# DWB 服务器升级：从 5.4 到 5.5{#dwb-server-upgrade-to}

从5.4安装升级Data Workbench6.1的服务器组件。

因此，从[!DNL Insight] 5.4升级到[!DNL Insight] 5.5相对简单。

您也可以使用下列步骤直接从 [!DNL Insight] 5.3 升级至 [!DNL Insight] 5.5。确保执行[从Insight 5.4升级到5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)部分和[从Insight 5.4升级到5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)部分中列出的所有升级任务。

1. 停止群集中除[!DNL Insight Master Server]之外的所有服务器上的[!DNL Insight Server]服务。

   1. 将新的 [!DNL ReportServer.exe] 和 [!DNL Insight.exe] 文件复制到 Software\Insight 文件夹中。

   1. 更新[!DNL Insight]客户端后，将[!DNL InsightServer.exe]和[!DNL InsightServer64.exe]文件复制到\Bin文件夹中。

   1. 等待[!DNL Insight Master Server]启动，然后验证通过[!DNL Connections]可视化运行的版本。

1. 在[!DNL Insight]客户端中群集的[!DNL Master Server]上：

   1. 生成现有 [!DNL Base] 配置文件的本地副本，然后对其重命名（例如 BaseBackup）。
   1. 将新的 [!DNL Base] 配置文件复制到 Profiles 文件夹中。
   1. 对 Transform 文件夹重复执行这两个步骤。

1. 将服务器包中的Scripts文件夹复制到[!DNL Master Server]中的Server安装目录中。
1. 将[!DNL Terrain Images.cfg.off]文件复制到[!DNL Master Server]的Components文件夹中。
   **将客户端软件从 [!DNL Insight] 5.4 升级至 5.5**

在 [!DNL Insight.cfg] 文件中，确保 Update Software 设置已设置为 true。
