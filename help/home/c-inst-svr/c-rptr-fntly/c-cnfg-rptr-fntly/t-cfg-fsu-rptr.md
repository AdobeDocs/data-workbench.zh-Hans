---
description: 有关安装和配置Insight Server FSU以与中继器一起使用的说明。
title: 为中继器配置 Insight Server FSU
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# 为中继器配置 Insight Server FSU{#configuring-an-insight-server-fsu-for-repeater}

有关安装和配置Insight Server FSU以与中继器一起使用的说明。

按顺序完成以下任务。 在每个步骤之后，将记录您必须进行的任何例外或更改，以便[!DNL Insight Server] FSU可用作中继服务器。

1. 按照[安装Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)中所述安装[!DNL Insight Server]程序文件。

   由于安装这些文件的计算机用于运行中继器，因此为安装目录提供一个描述性名称（如[!DNL D:\Adobe\Repeater]）会很有帮助。

1. 按照[下载和安装数字证书](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)中所述安装[!DNL Insight Server]数字证书。

   登录到Adobe许可证服务器后，请记得查找与指定中继器计算机的服务器通用名称匹配的证书名称。

1. 按照[检查端口设置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)中所述，检查[!DNL Communications.cfg]文件中的端口设置。

   如果分配的端口（端口和SSL端口）由同一台计算机上运行的另一个进程使用，则必须将端口分配更改为未使用的对。

1. 如有必要，请更改要在此计算机上收集和存储的[!DNL Sensor]数据的日志目录。 有关说明，请参阅[监视事件数据空间](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)。
1. 按照[更新访问控制文件](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)中所述，修改[!DNL Access Control.cfg]文件，以允许从[!DNL Insight]管理访问[!DNL Insight Server]。
1. 修改[!DNL server.address]文件，以按照[定义服务器的网络位置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)中的定义定义服务器的网络位置。
1. 设置Windows内存使用参数。
1. 按照[将Insight Server注册为Windows服务](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)中所述，将[!DNL Insight Server]注册为Windows服务。
