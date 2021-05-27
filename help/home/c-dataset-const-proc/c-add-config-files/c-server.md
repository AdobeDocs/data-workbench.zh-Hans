---
description: Server.cfg 文件中的 Sample Bytes（采样字节数）参数指定 Data Workbench 的数据缓存大小（以字节为单位）。
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 72%

---

# Server.cfg{#server-cfg}

Server.cfg 文件中的 Sample Bytes（采样字节数）参数指定 Data Workbench 的数据缓存大小（以字节为单位）。

默认值为 250e6。打开和保存[!DNL Server.cfg]文件的说明与[!DNL Log Processing Mode.cfg]的说明相同。 请参阅[Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a)。

>[!NOTE]
>
>由于此文件的参数会影响系统性能，因此请在进行任何更改之前联系Adobe。

您可以进一步限制连接到 Data Workbench Server 的 Data Workbench 计算机的数据缓存大小，方法是在 [!DNL Insight.cfg] 文件中设置 Maximum Sample Size（最大采样大小）参数。有关详细信息，请参阅《Data Workbench 用户指南》**。
