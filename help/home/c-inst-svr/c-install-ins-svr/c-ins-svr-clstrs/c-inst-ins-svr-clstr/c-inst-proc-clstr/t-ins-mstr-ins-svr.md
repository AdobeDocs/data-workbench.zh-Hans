---
description: 要使用群集，您必须在群集中指定一个Insight Server作为主控Insight Server。
title: 安装主 Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# 安装主 Insight Server{#installing-the-master-insight-server}

{{eol}}

要使用群集，您必须在群集中指定一个Insight Server作为主控Insight Server。

客户端组件，例如 [!DNL Insight] 或 [!DNL Report] 连接到主控 [!DNL Insight Server] 会话开始时。 在会话期间的后续时间点，客户端可能会连接到其他 [!DNL Insight Servers] 来执行查询。 客户端与另一个客户端之间的后续连接 [!DNL Insight Servers] 由主控 [!DNL Insight Server] 对客户是透明的。

除了为客户与其他客户之间的连接提供中介 [!DNL Insight Servers] 在群集中，主控 [!DNL Insight Server] 充当整个群集的中心管理点。 在管理群集时，需要更新主控 [!DNL Insight Server]. 您对主控 [!DNL Insight Server] 由另一个 [!DNL Insight Servers] 在群集中。

**安装主控[!DNL Insight Server]**

1. 确定哪台计算机将充当主控 [!DNL Insight Server].
1. 安装和配置 [!DNL Insight Server] (通常， [!DNL Insight Server] FSU)，如 [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. 安装 [!DNL Insight] 并配置与主控的连接 [!DNL Insight Server] 如 *[!DNL Insight]用户指南*.
