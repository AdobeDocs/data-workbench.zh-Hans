---
description: 通常，当您要处理并让Insight和报表的用户能够访问的数据量超过您群集当前配置的容量时，您需要将Insight Server DPU添加到现有群集。
title: 将 Insight Server DPU 添加到现有聚类
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# 将 Insight Server DPU 添加到现有聚类{#adding-an-insight-server-dpu-to-an-existing-cluster}

{{eol}}

通常，当您要处理并让Insight和报表的用户能够访问的数据量超过您群集当前配置的容量时，您需要将Insight Server DPU添加到现有群集。

## 更新主控服务器上的配置文件 {#section-7c9a23754a994d73b722d53f999f0e82}

在 [!DNL Insight]，打开 [!DNL Server Files Manager] 为您的主控 [!DNL Insight Server] (通常 [!DNL Insight Server] FSU)，并对要添加到群集的每个DPU执行以下操作：

1. 在主控上编辑地址文件 [!DNL Insight Server] 以包含新DPU的名称和地址，如 [将处理Insight Server添加到地址文件](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). 将新DPU的名称和地址添加到群集当前所在的组中 [!DNL Insight Servers] 列出。

1. 在主控上编辑访问控制文件 [!DNL Insight Server] 以包含新DPU的IP地址，如 [更新群集的访问控制文件](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## 安装新的Insight Server DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

此任务仅适用于Windows 32位。

1. 将以下目录从群集中的当前DPU之一复制到新DPU:

   * [!DNL Insight Server] 安装目录/bin/
   * [!DNL Insight Server] 安装目录/证书/
   * [!DNL Insight Server] 安装目录/组件/

1. 下载并安装适用于新DPU的数字证书，如 [下载并安装数字证书](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. 在新DPU上设置Windows内存使用参数。
1. 注册 [!DNL Insight Server] 作为新DPU计算机上的Windows服务，如 [将Insight Server注册为Windows服务](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. 检查跟踪日志，确保DPU正在同步到主控 [!DNL Insight Server].
1. 对要添加到群集的每个其他DPU重复步骤1至6。

## 将新的Insight Server DPU添加到数据集配置文件的处理服务器 {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

如果新DPU处理与群集中其他DPU相同的数据集，请将新DPU的通用名称添加到 [!DNL profile.cfg] 主控 [!DNL Insight Server] 如 [在Profile.cfg中指定处理服务器](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
