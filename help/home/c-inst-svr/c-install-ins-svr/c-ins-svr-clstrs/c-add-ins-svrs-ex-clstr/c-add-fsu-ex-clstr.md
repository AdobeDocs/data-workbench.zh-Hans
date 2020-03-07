---
description: 如果要将源数据存储在其他文件服务器上，或要为主Insight Server设置备份，则可能需要将Insight Server FSU添加到现有群集。
solution: Insight
title: 将Insight Server FSU添加到现有群集
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 将Insight Server FSU添加到现有群集{#adding-an-insight-server-fsu-to-an-existing-cluster}

如果要将源数据存储在其他文件服务器上，或要为主Insight Server设置备份，则可能需要将Insight Server FSU添加到现有群集。

要将 [!DNL Insight Server] FSU添加到现有群集，必须执行以下过程：

1. [更新主服务器上的配置文件](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [安装新Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [配置新Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## 更新主服务器上的配置文件 {#section-b5f21f2edb35493da4475de2cdeefca1}

在 [!DNL Insight]中，打开主视图 [!DNL Server Files Manager][!DNL Insight Server][!DNL Insight Server] （通常是FSU），然后对要添加到群集的每个FSU执行以下操作：

1. 编辑主服务器上的地址 [!DNL Insight Server] 文件，以包含新FSU的名称和地址，如将Processing Insight Servers添加到 [地址文件中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)。 将新FSU的名称和地址添加到其中列出群集当前内容的 [!DNL Insight Servers] 组。

1. 编辑主控件上的访问控制文 [!DNL Insight Server] 件，以包含新FSU的IP地址，如更新群集的 [访问控制文件中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)。

## 安装新Insight Server FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 在您当前的FSU上，制作安装目录的zip [!DNL Insight Server] 文件，然后将该文件复制到新的FSU。
1. 将文件解压缩到要放置软件的位 [!DNL Insight Server] 置。
1. 按照下载和安装数字证书中所述，下载并安装新FSU [的数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 在新FSU上设置Windows内存使用参数。
1. 更改文件的名 [!DNL .address] 称以反映FSU的名称，如定义服 [务器的网络位置中所述](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。

1. 如果新FSU上的驱动器结构与主FSU上的驱动器结构不同，则需要编辑文 [!DNL Disk Files.cfg] 件。

   1. Open the [!DNL Disk Files.cfg] file on the new FSU.
   1. 更新设置以匹配主FSU的驱动器，如监视数据集数据 [空间中所述](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)。
   1. 将文件保存在本地并保存到服务器。

1. 在新 [!DNL Insight Server] 的FSU计算机上注册为Windows服务，如将Insight Server注 [册为Windows服务中所述](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

1. 对于要添加到群集的每个附加FSU，重复步骤1至6。

## 配置新Insight Server FSU {#section-c39334c5bd754d5b98d41ad094333108}

以下过程提供了特定配置任务的说明。 按照适合您实施新FSU的说明操作。

**为源数据存储配置FSU**

如果新的FSU存储了群集上运行的数据集的其他源数据，则必须按照《数据集配置指南》的“日志处理配置文件”一章中的“配置文件服务器单元”中所述完成文件服务器 [!DNL Insight Server] 配置过程 **。

**使新FSU成为主FSU的备[!DNL Insight Server]份**

如果要使新FSU成为主FSU的备份 [!DNL Insight Server] （它用作群集的FSU），则必须在新（备份）FSU上修改同步文件，以便它与主FSU同步。

1. 在备份 [!DNL Insight Server] FSU上，使用将文 [!DNL Server Files Manager] 件夹中的文 [!DNL Synchronize.cfg] 件复制到 [!DNL Components for Processing Servers] 文件夹 [!DNL Components] 中。

1. 在中打 [!DNL Synchronize.cfg] 开文件(在文 [!DNL Components] 件夹中) [!DNL Insight]。

1. 查找指定“组件”目录位置的SynchronizeDir。 目录下可能列出了多个同步目录，因此您可能需要查看其中许多目录的内容（通过单击服务器号）以查找所需的服务器。
1. 编辑SynchronizeDir条目并添加另一个SynchronizeDir条目，如下例所示。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 使用新名称（如）保存修改后的文 [!DNL FSU_Synchronize.cfg] 件，以便不将其与群集中DPU [!DNL Synchronize.cfg] 上的文件混淆。

1. 使用将 [!DNL Server Files Manager] 重命名的文件的本地副本保存到服务器。 备份FSU从主 [!DNL Insight Server] FSU下载所标识目录中的文件，并在这些文件发生更改时从主 [!DNL Insight Server] FSU动态检索这些文件的更新副本。

