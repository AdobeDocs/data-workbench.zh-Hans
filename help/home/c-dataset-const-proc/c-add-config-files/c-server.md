---
description: Server.cfg 文件中的 Sample Bytes（采样字节数）参数指定 Data Workbench 的数据缓存大小（以字节为单位）。
solution: Analytics
title: Server.cfg
topic: Data workbench
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server.cfg{#server-cfg}

Server.cfg 文件中的 Sample Bytes（采样字节数）参数指定 Data Workbench 的数据缓存大小（以字节为单位）。

默认值为 250e6。Instructions for opening and saving the [!DNL Server.cfg] file are the same as those for [!DNL Log Processing Mode.cfg]. See [Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>由于此文件的参数影响系统性能，请在进行任何更改前与Adobe联系。

您可以进一步限制连接到 Data Workbench Server 的 Data Workbench 计算机的数据缓存大小，方法是在 [!DNL Insight.cfg] 文件中设置 Maximum Sample Size（最大采样大小）参数。有关详细信息，请参阅《Data Workbench 用户指南》**。
