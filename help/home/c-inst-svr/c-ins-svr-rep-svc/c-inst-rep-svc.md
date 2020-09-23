---
description: Insight Server复制服务允许您将在一台Insight Server计算机上收集和存储的事件数据传输到另一台Insight Server计算机。
solution: Analytics
title: 安装复制服务
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---


# 安装复制服务{#installing-the-replication-service}

Insight Server复制服务允许您将在一台Insight Server计算机上收集和存储的事件数据传输到另一台Insight Server计算机。

通常，收集和存储数据的计算机配置为作为计算机运 [!DNL Repeater] 行。 请参 [阅中继器功能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)。 由文 [!DNL Replication Service]件配置的计算机 [!DNL Replicate.cfg] 能够从计算机 [!DNL Insight Server] 检索数据并将其 [!DNL Repeater] 存储在本地。 机 [!DNL Insight Server] 器称为目标机。 多个 [!DNL Insight Server] DPU可以连接到一个事件 [!DNL Repeater] 数据，以请求该数据的副本以包含在多个数据集中。

您可以在具有 [!DNL Replication Service] 多层防火墙的网络基础架构中使用，在由防火墙隔开的组件之间实现单端口到单端口通信。

**安装[!DNL Replication Service]**

该 [!DNL Replicate.cfg] 文件应作为安装的一部 [!DNL Insight Server] 分安装。 您可以在安装目录的文 [!DNL Components] 件夹中找 [!DNL Insight Server] 到该文件。 如果您没有此文件，请与Adobe联系。
