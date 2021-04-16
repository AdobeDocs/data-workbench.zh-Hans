---
description: 安装和配置Report Server软件的步骤。
title: 安装概述
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
exl-id: 4ddc0761-a999-49ed-b0e4-12cf34e2688c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 8%

---

# 安装概述{#installation-overview}

安装和配置Report Server软件的步骤。

必须按顺序完成以下任务:

1. 安装报表服务器项目文件。
1. 下载并安装Report Server数字证书。 请参阅[下载和安装数字证书](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)。
1. 配置报表服务器与Data Workbench Server(InsightServer64.exe)之间的连接。 请参阅[配置与Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)的连接。
1. 使用语言文件（.zbin 文件）更新 Report Server。

   请参阅[使用语言文件（.zbin文件）](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b)更新报表服务器。 1.更新Data Workbench Server计算机上的访问控制文件，以使报表服务器能够访问Data Workbench Server。 请参阅[启用对Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc)的访问。
1. 编辑主控Data Workbench Server计算机上的通信文件，以在[!DNL Master Server Detailed Status]接口中显示报表服务器的状态。 请参阅[将Insight Server配置为显示报表](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8)的服务器状态。
1. 将报告注册为Windows服务。 请参阅[将报告注册为Windows服务](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6)。
