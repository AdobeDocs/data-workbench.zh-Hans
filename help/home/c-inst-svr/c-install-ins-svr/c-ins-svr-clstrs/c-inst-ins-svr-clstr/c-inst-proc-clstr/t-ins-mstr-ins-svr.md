---
description: 要使用群集，必须在群集中指定一个Insight Server作为主Insight Server。
solution: Insight
title: 安装主Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 安装主Insight Server{#installing-the-master-insight-server}

要使用群集，必须在群集中指定一个Insight Server作为主Insight Server。

客户端组件(如 [!DNL Insight] 或 [!DNL Report] )在会话开 [!DNL Insight Server] 始时连接到主设备。 在会话期间的后续时间点，客户端可以连接到群 [!DNL Insight Servers] 集中的其他位置以执行查询。 客户机与群集中的其他客户机之间的这 [!DNL Insight Servers] 些后续连接由主机调节，并且对客 [!DNL Insight Server] 户机是透明的。

除了代理客户端与群集中的其他 [!DNL Insight Servers] 设备之间的连接外，主设备 [!DNL Insight Server] 还充当整个群集的中心管理点。 管理群集时，将更新主群集 [!DNL Insight Server]。 您在主设备上所做的管理更改 [!DNL Insight Server] 由群集中的另一个 [!DNL Insight Servers] 用户检索。

**安装主视图[!DNL Insight Server]**

1. 确定哪台计算机将充当主计算机 [!DNL Insight Server]。
1. 如 [!DNL Insight Server] Insight Server [!DNL Insight Server] 中所述，在此计算 [机上安装和配置（通常为FSU）](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)。
1. 按照 [!DNL Insight] 用户指南中的说明，安 [!DNL Insight Server] 装并配置与主 *[!DNL Insight]设备的连接&#x200B;*。
