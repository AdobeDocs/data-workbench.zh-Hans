---
description: 升级Data Workbench 6.2和6.2.2的服务器组件。
title: DWB Server升级6.1到6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# DWB服务器升级：6.1至6.2{#dwb-server-upgrade-to}

升级Data Workbench 6.2和6.2.2的服务器组件。

## 6.2的升级问题 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* 为实施 Adobe SC 配置文件以使用 Analytics (SC/Insight) 数据源的用户配置了归因配置文件。默认情况下，将营销和转化事件作为在基于规则的模型中评估的默认交互。有关详细信息，请参阅[部署归因配置文件](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)。
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. 只有在将配置文件修改为非默认配置时，才会出现问题。
* If you have deleted unused fields in the [!DNL Dataset > Log Processing > SC Fields.cfg] file for the Adobe SC profile, you will need to update to accommodate updated field values used for the Attribution profile (see [Deploying the Attribution Profile](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)).

## 6.2.2的升级问题 {#section-8704a9ac358246cd81233dd0982d534f}

* 旧版配 **[!UICONTROL Browsers]** 置文 **[!UICONTROL Operating Systems]** 件中不会更新文件和查找 **[!UICONTROL Traffic]** 文件（例如，） [!DNL Lookups\Traffic\Browsers.txt)]。 Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* Data Workbench 6.2.1 是最后一个提供 32 位客户端应用程序下载的版本。将来所有的客户端应用程序下载都将是 64 位，并且会继续要求使用 Windows 7 或更新版本。由于从 6.1 版开始引入了 64 位应用程序，32 位应用程序的内存限制问题也随之得以解决。

>[!NOTE]
>
>32位版本的Data Workbench客户端应用程序在运行使用群集和评分功能的预测模型时可能遇到与内存限制相关的潜在问题。

