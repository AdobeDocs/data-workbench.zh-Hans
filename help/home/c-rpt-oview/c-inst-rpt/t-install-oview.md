---
description: 安装和配置报告服务器软件的步骤。
solution: Analytics
title: 安装概述
topic: Data workbench
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装概述{#installation-overview}

安装和配置报告服务器软件的步骤。

必须按顺序完成以下任务：

1. 安装Report Server程序文件。
1. 下载并安装Report Server数字证书。 See [Downloading and Installing the Digital Certificate](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
1. 配置报表服务器与数据工作台服务器(InsightServer64.exe)之间的连接。 See [Configuring the Connection to Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c).
1. 使用语言文件（.zbin 文件）更新 Report Server。

   See [Update Report Server with a language file (.zbin file)](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b). 1.更新Data Workbench Server计算机上的访问控制文件，以使Report Server能够访问Data Workbench Server。 请参 [阅启用对Insight Server的访问](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc)。
1. 编辑主Data Workbench Server计算机上的通信文件，以在界面中显示报表服务器的 [!DNL Master Server Detailed Status] 状态。 请参 [阅将Insight Server配置为显示报告的服务器状态](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8)。
1. 将报告注册为Windows服务。 请参 [阅将报告注册为Windows服务](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6)。

