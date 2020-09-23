---
description: 从5.4安装升级Data Workbench6.1的服务器组件。
solution: Analytics
title: DWB Server升级5.4到5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 39%

---


# DWB 服务器升级：从 5.4 到 5.5{#dwb-server-upgrade-to}

从5.4安装升级Data Workbench6.1的服务器组件。

Consequently, upgrading from [!DNL Insight] 5.4 to [!DNL Insight] 5.5 is relatively simple.

您也可以使用下列步骤直接从 [!DNL Insight] 5.3 升级至 [!DNL Insight] 5.5。确保执行从Insight 5.4升级到5.5 [部分以及从Insight 5.4升级到5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)[部分中列出的所有升级任务](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 。

1. 停止群 [!DNL Insight Server] 集中除服务外的所有服务器上的服务 [!DNL Insight Master Server]。

   1. 将新的 [!DNL ReportServer.exe] 和 [!DNL Insight.exe] 文件复制到 Software\Insight 文件夹中。

   1. After the [!DNL Insight] client has updated, copy the [!DNL InsightServer.exe] and [!DNL InsightServer64.exe] files into the \Bin folder.

   1. Wait for the [!DNL Insight Master Server] to start, then verify the version running via the [!DNL Connections] visualization.

1. 在客户端中 [!DNL Master Server] 的群 [!DNL Insight] 集上：

   1. 生成现有 [!DNL Base] 配置文件的本地副本，然后对其重命名（例如 BaseBackup）。
   1. 将新的 [!DNL Base] 配置文件复制到 Profiles 文件夹中。
   1. 对 Transform 文件夹重复执行这两个步骤。

1. Copy the Scripts folder from the server package onto the [!DNL Master Server] into the Server installation directory.
1. Copy the [!DNL Terrain Images.cfg.off] file into the Components folder of the [!DNL Master Server].
   **将客户端软件从[!DNL Insight]5.4 升级至 5.5**

在 [!DNL Insight.cfg] 文件中，确保 Update Software 设置已设置为 true。
