---
description: 要使用群集，您必须在群集中指定一个Insight Server作为主控Insight Server。
title: 安装主 Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# 安装主 Insight Server{#installing-the-master-insight-server}

要使用群集，您必须在群集中指定一个Insight Server作为主控Insight Server。

客户端组件（如[!DNL Insight]或[!DNL Report]）在会话开始时连接到主控的[!DNL Insight Server]。 在会话期间的后续时间点，客户端可能会连接到群集中的其他[!DNL Insight Servers]以执行查询。 客户机与群集中其他[!DNL Insight Servers]之间的这些后续连接由主控[!DNL Insight Server]调节，对客户机是透明的。

除了在客户机与群集中的其他[!DNL Insight Servers]之间进行连接代理外，主控[!DNL Insight Server]还充当整个群集的中心管理点。 在管理群集时，更新主控[!DNL Insight Server]。 您对主控[!DNL Insight Server]所做的管理更改将由群集中的其他[!DNL Insight Servers]进行检索。

**安装主控[!DNL Insight Server]**

1. 确定哪台计算机将充当主控[!DNL Insight Server]。
1. 如[Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)中所述，在此计算机上安装和配置[!DNL Insight Server]（通常为[!DNL Insight Server] FSU）。
1. 按照&#x200B;*[!DNL Insight]用户指南*&#x200B;中的说明，安装[!DNL Insight]并配置与主控[!DNL Insight Server]的连接。
