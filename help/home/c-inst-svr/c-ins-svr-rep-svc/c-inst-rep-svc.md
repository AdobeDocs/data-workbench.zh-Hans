---
description: Insight Server复制服务允许您将在一台Insight Server计算机上收集和存储的事件数据传输到另一台Insight Server计算机。
solution: Insight
title: 安装复制服务
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 安装复制服务{#installing-the-replication-service}

Insight Server复制服务允许您将在一台Insight Server计算机上收集和存储的事件数据传输到另一台Insight Server计算机。

通常，收集和存储数据的计算机配置为作为计算机运 [!DNL Repeater] 行。 请参 [阅中继器功能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)。 由文 [!DNL Replication Service]件配置的计算机 [!DNL Replicate.cfg] 能够从计算机中检索数据并 [!DNL Insight Server][!DNL Repeater] 将其存储在本地。 计 [!DNL Insight Server] 算机称为目标计算机。 多个 [!DNL Insight Server] DPU可以连接到一个DPU以请 [!DNL Repeater] 求事件数据的副本以包含在多个数据集中。

您可以使用 [!DNL Replication Service] 具有多层防火墙的网络基础架构中的防火墙，实现由防火墙隔开的组件之间的单端口到单端口通信。

**安装[!DNL Replication Service]**

该 [!DNL Replicate.cfg] 文件应作为安装的一部分进行 [!DNL Insight Server] 安装。 您可以在安装目录的文 [!DNL Components] 件夹中找到 [!DNL Insight Server] 该文件。 如果您没有此文件，请与Adobe联系。
