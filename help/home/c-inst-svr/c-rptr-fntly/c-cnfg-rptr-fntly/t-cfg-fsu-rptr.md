---
description: 安装和配置Insight Server FSU以与Repeater一起使用的说明。
solution: Analytics
title: 为中继器配置 Insight Server FSU
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---


# 为中继器配置 Insight Server FSU{#configuring-an-insight-server-fsu-for-repeater}

安装和配置Insight Server FSU以与Repeater一起使用的说明。

按顺序完成以下任务。 在每个步骤后，都会记录您必须进行的 [!DNL Insight Server] 任何例外或更改，以便FSU可用作中继服务器。

1. 按照安 [!DNL Insight Server] 装Insight Server中所述安 [装项目文件](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)。

   由于安装这些文件的计算机用于运行Repeater，因此为安装目录提供描述性名称(如 [!DNL D:\Adobe\Repeater])。

1. 按照下 [!DNL Insight Server] 载和安装数字证 [书中的说明安装数字证书](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。

   登录到Adobe许可证服务器后，请记住查找与指定中继器计算机的服务器通用名称相匹配的证书名称。

1. 按检查端口设置中 [!DNL Communications.cfg] 所述检查文 [件中的端口设置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)。

   如果在同一台计算机上运行的另一个进程使用分配的端口（端口和SSL端口），则必须将端口分配更改为未使用的对。

1. 如有必要，请更改要在此计算机上 [!DNL Sensor] 收集和存储的数据的日志目录。 有关说明，请参 [阅监视事件数据空间](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)。
1. 修改文 [!DNL Access Control.cfg] 件，允许从更新访问控制 [!DNL Insight Server] 文件 [!DNL Insight] 中进行管 [理访问](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)。
1. 修改文 [!DNL server.address] 件以定义服务器的网络位置，如 [定义服务器的网络位置中所定义](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。
1. 设置Windows内存使用参数。
1. 注 [!DNL Insight Server] 册为Windows服务，如注 [册Insight Server为Windows服务中所述](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。
