---
description: Insight Server复制服务允许您将收集并存储在一台Insight Server计算机上的事件数据传输到另一台Insight Server计算机。
title: 安装复制服务
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# 安装复制服务{#installing-the-replication-service}

{{eol}}

Insight Server复制服务允许您将收集并存储在一台Insight Server计算机上的事件数据传输到另一台Insight Server计算机。

通常，收集和存储数据的计算机配置为作为 [!DNL Repeater] 机器。 请参阅 [中继器功能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). 的 [!DNL Replication Service]，由 [!DNL Replicate.cfg] 文件，启用 [!DNL Insight Server] 从中检索数据的计算机 [!DNL Repeater] 机器并将其存储在本地。 的 [!DNL Insight Server] 计算机称为目标计算机。 多个 [!DNL Insight Server] DPU可以连接到单个 [!DNL Repeater] 请求事件数据的副本以包含在多个数据集中。

您可以使用 [!DNL Replication Service] 在具有多层防火墙的网络基础架构中，实现由防火墙分隔的组件之间的单端口到单端口通信。

**安装[!DNL Replication Service]**

的 [!DNL Replicate.cfg] 文件应作为 [!DNL Insight Server] 安装。 您可以在 [!DNL Components] 文件夹 [!DNL Insight Server] 安装目录。 如果您没有此文件，请联系Adobe。
