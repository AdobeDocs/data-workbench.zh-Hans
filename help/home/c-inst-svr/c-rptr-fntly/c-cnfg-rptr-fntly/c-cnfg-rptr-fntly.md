---
description: 中继器功能使Insight Server FSU能够从一个或多个源接收传感器获取的事件数据，并将数据复制到运行Insight Server复制服务的一个或多个Insight Server FSU。
solution: Analytics
title: 配置中继器功能
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 17%

---


# 配置中继器功能{#configuring-repeater-functionality}

中继器功能使Insight Server FSU能够从一个或多个源接收传感器获取的事件数据，并将数据复制到运行Insight Server复制服务的一个或多个Insight Server FSU。

See [Insight Server Replication Service](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). 此功能允许将数据复制到冗余设施以用于灾难恢复目的。 目标服务器充当网络客户端，连接到源FSU以请求事件数据的副本以包含在多个数据集中。

您可以在具有多层防火墙的网络基础架构中使用中继器功能，在由防火墙隔开的组件之间实现单端口到单端口通信。

有关安装、配置和运行 [!DNL Repeater] 的系统要求的信息，请参阅“最低系统要求”**&#x200B;文档。

要进行安 [!DNL Repeater]装，您必须执行以下两个过程中列出的步骤：

* [为中继器配置 Insight Server FSU](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [为目标计算机配置访问控制](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

如果网络防火墙允许从访 [!DNL Repeater] 问您 [!DNL Insight]的连接，您可以创建连接，如创 [建Insight和Repeater之间的连接中所述](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)。
