---
description: 如果要在其他文件服务器上存储源数据，或要为主控的Insight Server设置备份，则可能需要将Insight Server FSU添加到现有聚类。
title: 将 Insight Server FSU 添加到现有聚类
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 将 Insight Server FSU 添加到现有聚类{#adding-an-insight-server-fsu-to-an-existing-cluster}

如果要在其他文件服务器上存储源数据，或要为主控的Insight Server设置备份，则可能需要将Insight Server FSU添加到现有聚类。

要将[!DNL Insight Server] FSU添加到现有群集，必须执行以下步骤：

1. [更新主控服务器上的配置文件](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [安装新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [配置新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## 更新主控服务器{#section-b5f21f2edb35493da4475de2cdeefca1}上的配置文件

在[!DNL Insight]中，为主控的[!DNL Insight Server]（通常为[!DNL Insight Server] FSU）打开[!DNL Server Files Manager] ，并对要添加到群集的每个FSU执行以下操作：

1. 编辑主控[!DNL Insight Server]上的地址文件，以包含新FSU的名称和地址，如[将处理Insight Server添加到地址文件](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)中所述。 将新FSU的名称和地址添加到群集当前[!DNL Insight Servers]所在的组中。

1. 编辑主控[!DNL Insight Server]上的访问控制文件，以包含新FSU的IP地址，如[更新群集](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)的访问控制文件中所述。

## 安装新的Insight Server FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 在当前FSU上，生成[!DNL Insight Server]安装目录的zip文件，然后将该文件复制到新FSU。
1. 将文件解压缩到要放置[!DNL Insight Server]软件的位置。
1. 按照[下载和安装数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)中所述，下载并安装新FSU的数字证书。
1. 在新FSU上设置Windows内存使用参数。
1. 更改[!DNL .address]文件的名称，以反映[定义服务器的网络位置](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)中所述的FSU的名称。

1. 如果新FSU上的驱动器结构与主FSU上的驱动器结构不同，则需要编辑[!DNL Disk Files.cfg]文件。

   1. 在新FSU上打开[!DNL Disk Files.cfg]文件。
   1. 更新设置以匹配主FSU的驱动器，如[监控数据集数据空间](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)中所述。
   1. 将文件保存在本地并保存到服务器。

1. 按照[将Insight Server注册为Windows服务](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)中所述，在新的FSU计算机上注册[!DNL Insight Server]作为Windows服务。

1. 对要添加到群集的每个附加FSU重复步骤1至6。

## 配置新的Insight Server FSU {#section-c39334c5bd754d5b98d41ad094333108}

以下过程提供了有关特定配置任务的说明。 按照适合您实施新FSU的说明操作。

**为源数据存储配置FSU**

如果新FSU存储了群集上运行的数据集的其他源数据，则必须按照&#x200B;*数据集配置指南*&#x200B;的“日志处理配置文件”一章中的“配置[!DNL Insight Server]文件服务器单元”中所述，完成文件服务器配置过程。

**为新FSU备份主控FSU  [!DNL Insight Server]**

如果要将新FSU作为主控[!DNL Insight Server]（用作群集的FSU）的备份，则必须在新（备份）FSU上修改同步文件，以便它与主控FSU同步。

1. 在备份[!DNL Insight Server] FSU中，使用[!DNL Server Files Manager]将[!DNL Components for Processing Servers]文件夹中的[!DNL Synchronize.cfg]文件复制到[!DNL Components]文件夹。

1. 打开[!DNL Synchronize.cfg]文件（在[!DNL Components]文件夹中），位于[!DNL Insight]中。

1. 查找指定Components目录位置的SynchronizeDir。 目录下可能列出了多个同步目录，因此您可能需要查看其中许多目录的内容（通过单击服务器号）以找到所需的服务器。
1. 编辑SynchronizeDir条目并添加第二个SynchronizeDir条目，如以下示例所示。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 使用新名称（如[!DNL FSU_Synchronize.cfg]）保存修改后的文件，以便不要将其与群集中DPU上的[!DNL Synchronize.cfg]文件混淆。

1. 使用[!DNL Server Files Manager]将重命名文件的本地副本保存到服务器。 备份FSU从主控[!DNL Insight Server] FSU下载已标识目录中的文件，并在这些文件发生更改时从主控[!DNL Insight Server] FSU动态检索这些文件的更新副本。
