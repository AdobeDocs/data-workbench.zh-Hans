---
description: Insight Server复制服务允许您将在一台Insight Server计算机上收集和存储的事件数据传输到另一台Insight Server计算机。
title: 安装复制服务
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# 安装复制服务{#installing-the-replication-service}

Insight Server复制服务允许您将在一台Insight Server计算机上收集和存储的事件数据传输到另一台Insight Server计算机。

通常，收集和存储数据的计算机配置为作为[!DNL Repeater]计算机运行。 请参阅[Repeater Functionality](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)。 由[!DNL Replicate.cfg]文件配置的[!DNL Replication Service]使[!DNL Insight Server]计算机能够从[!DNL Repeater]计算机检索数据并将其存储在本地。 [!DNL Insight Server]计算机称为目标计算机。 多个[!DNL Insight Server] DPU可以连接到单个[!DNL Repeater]以请求事件数据的副本以包含在多个数据集中。

您可以在网络基础架构中使用[!DNL Replication Service]，该网络基础架构具有多层防火墙，以实现由防火墙隔离的组件之间的单端口到单端口通信。

**安装[!DNL Replication Service]**

[!DNL Replicate.cfg]文件应作为[!DNL Insight Server]安装的一部分进行安装。 可以在[!DNL Insight Server]安装目录的[!DNL Components]文件夹中找到该文件。 如果您没有此文件，请与Adobe联系。
