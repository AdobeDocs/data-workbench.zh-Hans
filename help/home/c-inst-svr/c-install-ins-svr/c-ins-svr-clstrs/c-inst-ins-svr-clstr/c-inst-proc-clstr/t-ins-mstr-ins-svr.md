---
description: 要使用群集，必须在群集中指定一个Insight Server作为主控Insight Server。
solution: Analytics
title: 安装主 Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---


# 安装主 Insight Server{#installing-the-master-insight-server}

要使用群集，必须在群集中指定一个Insight Server作为主控Insight Server。

客户端组件( [!DNL Insight] 如 [!DNL Report] 或)在会 [!DNL Insight Server] 话开始时连接到主控。 在会话期间的后续点，客户端可能会连接到群 [!DNL Insight Servers] 集中的其他节点以执行查询。 客户机和群集中的其他机 [!DNL Insight Servers] 器之间的这些后续连接由主控调 [!DNL Insight Server] 节，对客户机透明。

除了代理客户端与群集中的其 [!DNL Insight Servers] 他客户端之间的连接外，主控 [!DNL Insight Server] 还充当整个群集的中心管理点。 管理群集时，将更新主控 [!DNL Insight Server]。 您对主控所做的管理更改 [!DNL Insight Server] 由群集中的其 [!DNL Insight Servers] 他用户检索。

**安装主控[!DNL Insight Server]**

1. 确定哪台计算机将充当主控 [!DNL Insight Server]。
1. 如Insight Server [!DNL Insight Server] 中所述， [!DNL Insight Server] 在此计算机上安装和配 [置（通常为FSU）](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)。
1. 按 [!DNL Insight] 照用户指南中的 [!DNL Insight Server] 说明安装和配置主控 *[!DNL Insight]连接*。
