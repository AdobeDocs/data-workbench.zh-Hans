---
description: 通常，当要处理并让Insight和Report的用户能够访问的数据量超过群集当前配置的容量时，您需要将Insight Server DPU添加到现有群集。
solution: Analytics
title: 将 Insight Server DPU 添加到现有聚类
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---


# 将 Insight Server DPU 添加到现有聚类{#adding-an-insight-server-dpu-to-an-existing-cluster}

通常，当要处理并让Insight和Report的用户能够访问的数据量超过群集当前配置的容量时，您需要将Insight Server DPU添加到现有群集。

## 更新主控服务器上的配置文件 {#section-7c9a23754a994d73b722d53f999f0e82}

在 [!DNL Insight]中，为主控 [!DNL Server Files Manager] (通 [!DNL Insight Server][!DNL Insight Server] 常是FSU)打开，并对要添加到群集的每个DPU执行以下操作：

1. 在主控上编辑地址文 [!DNL Insight Server] 件，以包括新DPU的名称和地址，如将处理Insight Server [添加到地址文件中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)。 将新DPU的名称和地址添加到其中列出群集当前内容的 [!DNL Insight Servers] 组。

1. 编辑主控上的访问控制 [!DNL Insight Server] 文件，以包括新DPU的IP地址，如更新群 [集的访问控制文件中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)。

## 安装新Insight Server DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

此任务仅适用于Windows 32位。

1. 将以下目录从群集中的当前DPU之一复制到新DPU:

   * [!DNL Insight Server] 安装目录/bin/
   * [!DNL Insight Server] 安装目录／证书/
   * [!DNL Insight Server] 安装目录／组件/

1. 下载并安装新DPU的数字证书，如下载和安 [装数字证书中所述](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 在新DPU上设置Windows内存使用参数。
1. 在新 [!DNL Insight Server] 的DPU计算机上注册为Windows服务，如 [将Insight Server注册为Windows服务中所述](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

1. 检查跟踪日志，确保DPU正在同步到主控 [!DNL Insight Server]。
1. 对要添加到群集的每个附加DPU重复步骤1到6。

## 将新Insight Server DPU添加到数据集用户档案的处理服务器 {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

如果新DPU处理与群集中的其他DPU相同的数据集，请将新DPU的公用名称添加到主控文 [!DNL profile.cfg] 件中， [!DNL Insight Server] 如在 [用户档案.cfg中指定处理服务器中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)。
