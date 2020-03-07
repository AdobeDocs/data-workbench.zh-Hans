---
description: Data Workbench将配置文件下载到您的计算机。
title: 配置文件
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profiles{#profiles}

Data Workbench将配置文件下载到您的计算机。

If you are loading a profile for the first time, you must have a network connection to the [!DNL Data Workbench server] and be working online so that Data Workbench can download the necessary files from the [!DNL Data Workbench server].

下载配置文件的过程可能需要几分钟时间。在数据缓存开始填充之前，不要开始使用配置文件，但也不必等到填满。在加载配置文件时，通过查看状态栏，可以跟踪数据缓存的进度、配置文件同步的进度以及最新处理数据的日期和时间。

>[!NOTE]
>
>在数据缓存开始填充之前，您不会在可视化中看到所添加的数据。

下次加载配置文件时，只有当您拥有到 [!DNL Data Workbench server] 的网络连接并且联机工作时，才会下载配置文件及其数据的更新。如果您脱机工作，则会从计算机的缓存中加载配置文件及其数据。这种情况下，您查看的配置文件及数据的版本是上次您使用配置文件联机工作时下载的版本。有关联机工作与脱机工作的详细信息，请参阅[脱机工作和联机工作](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54)。

When you need to change your profile (using the [!DNL Profile Manager] or the [!DNL Server Files Manager]), you should work online to ensure that you have the most up-to-date version of the profile. 有关和的详细信 [!DNL Profile Manager] 息，请参 [!DNL Server Files Manager]阅管 [理界面](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)。

如果您无法访问或加载配置文件，则可能需要确认以下事项：

* 拥有到配置文件所在的 [!DNL Data Workbench server] 计算机的网络连接。
* 拥有访问配置文件的适当权限。

如需帮助，请与您的系统管理员联系。

## Loading or switching profiles {#section-c50499d7d8084d7cadfada52df33f5f4}

1. 启动Data Workbench。
1. In the side bar, click the profile name and click **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, where *profile name* is the profile with which you want to work.

   ![](assets/sidebar_profile.png)

如果您是首次加载所选择的配置文件，则可能需要几分钟时间才能下载足够的数据来填充可视化。

## Accessing a profile on a cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

访问运行在

ata Workbench Server群集仅标识Data Workbench配置文件( [!DNL Insight.cfg])中的主Data Workbench Server。 从Data Workbench用户的角度来看，只有一台Data Workbench Server（主Data Workbench Server）可访问配置文件。 但是，分析员的查询请求可以定向到群集中的任何Data Workbench Server。

For more information about profiles running on a Data Workbench Server cluster, see the *Server Products Installation and Administration Guide*.
