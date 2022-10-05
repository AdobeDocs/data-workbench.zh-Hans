---
description: 中继器功能的管理任务与Insight Server的管理任务非常相似。
title: 管理中继器
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
exl-id: 5c7a4f95-be4b-4c2c-8dea-19037ba0b5cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---

# 管理中继器{#administering-repeater}

{{eol}}

中继器功能的管理任务与Insight Server的管理任务非常相似。

下列管理任务适用；例外或更改 [!DNL Insight Server] 在每个步骤之后，都记下DPU可以与中继服务器一起使用。

* [重新验证数字证书](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [确认服务正在运行](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) 在“服务”控制面板的服务列表中，查找“中继器”。

* [配置访问控制](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [监控磁盘空间](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) 应用于中继服务器的数据类型包括事件、操作系统和系统数据。 如果您使用中继服务器进行备份存储，并且有必要在计算机上提供更多的数据存储空间，则可以将除当前日志文件之外的所有日志文件移动到另一台计算机或数据存储介质（zip驱动器、磁带等）。 移动数据不需要停止中继器服务。

   >[!NOTE]
   >
   >您应该验证 [!DNL .vsl] 文件，然后再从中继器删除其中任何一个文件。

* [配置管理警报](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [监控管理事件](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [监控审计日志](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [配置通信](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [重新启动服务](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)  [!DNL Repeater] 功能旨在持续运行。 如果重新启动计算机，中继器将自动重新启动。 如果需要手动启动和停止中继器，可以使用Windows中的“服务”控制面板执行此操作。
