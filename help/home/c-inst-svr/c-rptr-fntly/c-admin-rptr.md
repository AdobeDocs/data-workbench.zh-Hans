---
description: 重复器功能的管理任务与Insight Server的管理任务非常相似。
solution: Insight
title: 管理中继器
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 管理中继器{#administering-repeater}

重复器功能的管理任务与Insight Server的管理任务非常相似。

适用下列管理任务：在每个步骤后都会记录您必须做的例外或更改，以便 [!DNL Insight Server] DPU可以与中继服务器一起使用。

* [重新验证数字证书](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [确认服务正在运行](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) “服务”控制面板中的服务列表中，查找“Repeater”。

* [配置访问控制](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [监视磁盘空间](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) 。适用于中继器服务器的数据类型包括事件、操作系统和系统数据。 如果您使用Repeater服务器进行备份存储，并且有必要在计算机上提供更多的数据存储空间，则可以将除当前最新日志文件以外的所有日志文件移动到另一台计算机或数据存储介质（zip驱动器、磁带等）。 移动数据不要求您停止Repeater服务。

   >[!NOTE]
   >
   >在从Repeater中删除文件的备份副本之前，您应 [!DNL .vsl] 验证其完整性。

* [配置管理警报](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [监视管理事件](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [监视审计日志](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [配置通信](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [重新启动服务](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)[!DNL Repeater] 功能设计为可连续运行。 如果重新启动计算机，则中继器会自动重新启动。 如果需要手动启动和停止中继器，可以使用Windows中的“服务”控制面板执行此操作。

