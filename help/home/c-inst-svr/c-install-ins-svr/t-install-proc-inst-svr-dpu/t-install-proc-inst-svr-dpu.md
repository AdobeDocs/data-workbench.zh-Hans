---
description: 有关安装Insight Server DPU并将其配置为用于管理用途的详细说明。
title: Insight Server DPU 的安装过程
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Insight Server DPU 的安装过程{#installation-procedures-for-an-insight-server-dpu}

有关安装Insight Server DPU并将其配置为用于管理用途的详细说明。

要安装和配置[!DNL Insight Server] DPU，您必须按顺序完成以下任务:

1. 安装[!DNL Insight Server]项目文件。 请参阅[安装Insight Server项目文件](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)。
1. 下载并安装[!DNL Insight Server]数字证书。 请参阅[下载和安装数字证书](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 检查[!DNL Communications.cfg]文件中的端口设置。 请参阅[检查端口设置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)。
1. 修改[!DNL Access Control.cfg]文件，以允许从[!DNL Insight]对[!DNL Insight Server]进行管理访问。 请参阅[更新访问控制文件](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)。
1. 修改[!DNL server.address]文件以定义服务器的网络位置。 请参阅[定义服务器的网络位置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。
1. （可选）修改[!DNL Disk Files.cfg]文件以指定处理数据的存储位置。 请参阅[配置数据集的位置(temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)。
1. 安装用户档案和查找文件。 请参阅[安装用户档案和查找文件](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc)。
1. 设置Microsoft Windows内存使用参数。
1. 将[!DNL Insight Server]注册为Windows服务。 请参阅[将Insight Server注册为Windows服务](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。
