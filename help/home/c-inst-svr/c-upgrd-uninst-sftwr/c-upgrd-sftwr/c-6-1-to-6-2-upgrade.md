---
description: 升级Data Workbench6.2和6.2.2的服务器组件。
title: DWB服务器升级6.1到6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 40%

---

# DWB 服务器升级：从 6.1 至 6.2{#dwb-server-upgrade-to}

升级Data Workbench6.2和6.2.2的服务器组件。

## 6.2的升级问题 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* 为实施 Adobe SC 配置文件以使用 Analytics (SC/Insight) 数据源的用户配置了归因配置文件。默认情况下，将营销和转化事件作为在基于规则的模型中评估的默认交互。有关详细信息，请参阅[部署归因配置文件](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)。
* 对于升级到Data Workbench6.2的AdobeSC配置文件的用户，如果您没有使用默认配置，请验证[!DNL SC Fields.cfg]文件中的[!DNL x-bot_id]值是否正确解码，以及[!DNL x-bot_id]字段是否正确列在[!DNL Decoding Instructions.cfg]和[!DNL Exclude Hit.cfg]文件中。 只有在将配置文件修改为非默认配置时，才会出现问题。
* 如果您在[!DNL Dataset > Log Processing > SC Fields.cfg]文件中删除了AdobeSC配置文件的未使用字段，则需要更新以适应用于归因配置文件的更新字段值（请参阅[部署归因配置文件](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)）。

## 6.2.2的升级问题 {#section-8704a9ac358246cd81233dd0982d534f}

* **[!UICONTROL Browsers]**&#x200B;和&#x200B;**[!UICONTROL Operating Systems]**&#x200B;查找文件将不会在旧版&#x200B;**[!UICONTROL Traffic]**&#x200B;配置文件中更新（例如，[!DNL Lookups\Traffic\Browsers.txt)]）。 配置&#x200B;**[!UICONTROL Traffic]**&#x200B;配置文件将使用DeviceAtlas包([!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle])来提供此配置信息。
* Data Workbench 6.2.1 是最后一个提供 32 位客户端应用程序下载的版本。将来所有的客户端应用程序下载都将是 64 位，并且会继续要求使用 Windows 7 或更新版本。由于从 6.1 版开始引入了 64 位应用程序，32 位应用程序的内存限制问题也随之得以解决。

>[!NOTE]
>
>在使用聚类和评分功能运行预测模型时，32位版本的Data Workbench客户端应用程序可能会遇到与内存限制相关的潜在问题。
