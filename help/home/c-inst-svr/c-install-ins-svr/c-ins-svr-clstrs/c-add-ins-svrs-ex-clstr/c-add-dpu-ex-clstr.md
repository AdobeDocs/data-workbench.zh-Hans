---
description: 通常，当要处理并让Insight和Report的用户能够访问的数据量超过群集当前配置的容量时，您需要将Insight Server DPU添加到现有群集。
solution: Insight
title: 将Insight Server DPU添加到现有群集
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 将Insight Server DPU添加到现有群集{#adding-an-insight-server-dpu-to-an-existing-cluster}

通常，当要处理并让Insight和Report的用户能够访问的数据量超过群集当前配置的容量时，您需要将Insight Server DPU添加到现有群集。

## 更新主服务器上的配置文件 {#section-7c9a23754a994d73b722d53f999f0e82}

在 [!DNL Insight]中，打开主视图 [!DNL Server Files Manager][!DNL Insight Server][!DNL Insight Server] （通常是FSU），然后对要添加到群集的每个DPU执行以下操作：

1. 编辑主服务器上的地址 [!DNL Insight Server] 文件，以包含新DPU的名称和地址，如将Processing Insight Servers添 [加到地址文件中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)。 将新DPU的名称和地址添加到群集当前所在的组 [!DNL Insight Servers] 中。

1. 编辑主控件上的访问控制文 [!DNL Insight Server] 件，以包含新DPU的IP地址，如更新群集的 [访问控制文件中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)。

## 安装新Insight Server DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

此任务仅适用于Windows 32位。

1. 将以下目录从群集中的当前DPU之一复制到新DPU:

   * [!DNL Insight Server] 安装目录/bin/
   * [!DNL Insight Server] 安装目录／证书/
   * [!DNL Insight Server] 安装目录／组件/

1. 按照下载和安装数字证书中所述，下载并安装新DPU [的数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 在新DPU上设置Windows内存使用参数。
1. 在新 [!DNL Insight Server] 的DPU计算机上注册为Windows服务，如将Insight Server注 [册为Windows服务中所述](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

1. 检查跟踪日志，确保DPU正在同步到主设备 [!DNL Insight Server]。
1. 对于要添加到群集的每个附加DPU，重复步骤1至6。

## 将新Insight Server DPU添加到数据集配置文件的处理服务器 {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

如果新DPU处理与群集中的其他DPU相同的数据集，请将新DPU的公用名称添加到主文件中，如Profile.cfg中的“指定处理服务器”中所 [!DNL profile.cfg] 述 [!DNL Insight Server][](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)。
