---
description: 如果要将源数据存储在其他文件服务器上，或者要为主控Insight Server设置备份，则可能需要将Insight Server FSU添加到现有群集。
title: 将 Insight Server FSU 添加到现有聚类
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 将 Insight Server FSU 添加到现有聚类{#adding-an-insight-server-fsu-to-an-existing-cluster}

如果要将源数据存储在其他文件服务器上，或者要为主控Insight Server设置备份，则可能需要将Insight Server FSU添加到现有群集。

要将[!DNL Insight Server] FSU添加到现有群集，必须执行以下过程：

1. [更新主控服务器上的配置文件](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [安装新Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [配置新Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## 更新主控服务器{#section-b5f21f2edb35493da4475de2cdeefca1}上的配置文件

在[!DNL Insight]中，为您的主控[!DNL Insight Server]（通常为[!DNL Insight Server] FSU）打开[!DNL Server Files Manager]，并对要添加到群集的每个FSU执行以下操作：

1. 在主控[!DNL Insight Server]上编辑地址文件，以包括新FSU的名称和地址，如[将处理分析服务器添加到地址文件](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)中所述。 将新FSU的名称和地址添加到群集当前[!DNL Insight Servers]所在的组中。

1. 在主控[!DNL Insight Server]上编辑访问控制文件，以包括新FSU的IP地址，如[更新群集](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)的访问控制文件中所述。

## 安装新Insight Server FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 在您当前的FSU上，制作[!DNL Insight Server]安装目录的zip文件，并将该文件复制到新的FSU。
1. 将文件解压缩到要放置[!DNL Insight Server]软件的位置。
1. 下载并安装新FSU的数字证书，如[下载和安装数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)中所述。
1. 在新FSU上设置Windows内存使用参数。
1. 更改[!DNL .address]文件的名称以反映FSU的名称，如[定义服务器的网络位置](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)中所述。

1. 如果新FSU上的驱动器结构与主FSU上的驱动器结构不同，则需要编辑[!DNL Disk Files.cfg]文件。

   1. 在新FSU上打开[!DNL Disk Files.cfg]文件。
   1. 更新设置以匹配主FSU的驱动器，如[监视数据集数据空间](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)中所述。
   1. 将文件保存在本地并保存到服务器。

1. 在新的FSU计算机上将[!DNL Insight Server]注册为Windows服务](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)中所述的Windows服务。[

1. 对要添加到群集的每个附加FSU重复步骤1到6。

## 配置新Insight Server FSU {#section-c39334c5bd754d5b98d41ad094333108}

以下过程提供了特定配置任务的说明。 按照适合您实施新FSU的说明操作。

**为源数据存储配置FSU**

如果新FSU存储群集上运行的数据集的其他源数据，则必须按照&#x200B;*Dataset Configuration Guide*&#x200B;的“Log Processing Configuration File”一章中的“Configuring a [!DNL Insight Server] File Server Unit”中所述完成文件服务器配置过程。

**使新FSU成为主控FSU的备 [!DNL Insight Server] 份**

如果要使新FSU成为主控[!DNL Insight Server]（它用作群集的FSU）的备份，则必须修改新（备份）FSU上的同步文件，以便它与主控FSU同步。

1. 在备份[!DNL Insight Server] FSU上，使用[!DNL Server Files Manager]将[!DNL Components for Processing Servers]文件夹中的[!DNL Synchronize.cfg]文件复制到[!DNL Components]文件夹。

1. 打开[!DNL Insight]中的[!DNL Synchronize.cfg]文件（位于[!DNL Components]文件夹中）。

1. 查找指定Components目录位置的SynchronizeDir。 目录下可能列出了多个同步目录，因此您可能需要视图其中许多目录的内容（通过单击服务器号）来查找所需的服务器)。
1. 编辑SynchronizeDir项并添加第二个SynchronizeDir项，如下例所示。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 使用新名称（如[!DNL FSU_Synchronize.cfg]）保存修改后的文件，以便不将其与群集中DPU上的[!DNL Synchronize.cfg]文件混淆。

1. 使用[!DNL Server Files Manager]将重命名的文件的本地副本保存到服务器。 备份FSU从主控[!DNL Insight Server] FSU下载所标识目录中的文件，并在这些文件发生更改时从主控[!DNL Insight Server] FSU动态检索这些文件的更新副本。
