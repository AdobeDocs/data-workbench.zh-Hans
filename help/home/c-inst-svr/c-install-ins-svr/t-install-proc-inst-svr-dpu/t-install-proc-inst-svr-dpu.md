---
description: 有关安装Insight Server DPU并将其配置为用于管理用途的详细说明。
solution: Analytics
title: Insight Server DPU 的安装过程
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---


# Insight Server DPU 的安装过程{#installation-procedures-for-an-insight-server-dpu}

有关安装Insight Server DPU并将其配置为用于管理用途的详细说明。

要安装和配置DPU, [!DNL Insight Server] 您必须按顺序完成以下任务:

1. 安装 [!DNL Insight Server] 项目文件。 See [Installing the Insight Server Program Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Download and install the [!DNL Insight Server] digital certificate. See [Downloading and Installing the Digital Certificates](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. 检查文件中的端口 [!DNL Communications.cfg] 设置。 See [Checking the Port Settings](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. 修改文 [!DNL Access Control.cfg] 件，以允许从进行管理 [!DNL Insight Server] 访问 [!DNL Insight]。 See [Updating the Access Control File](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. 修改文 [!DNL server.address] 件以定义服务器的网络位置。 See [Defining the Server&#39;s Network Location](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. （可选）修改文 [!DNL Disk Files.cfg] 件以指定存储已处理数据的位置。 See [Configuring the Location of the Dataset (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. 安装用户档案和查找文件。 See [Installing Profiles and Lookup Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. 设置Microsoft Windows内存使用参数。
1. 注册 [!DNL Insight Server] 为Windows服务。 See [Registering Insight Server as a Windows Service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
