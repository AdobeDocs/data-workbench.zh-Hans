---
description: Data Workbench将用户档案下载到您的计算机。
title: 配置文件
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 50%

---

# 配置文件{#profiles}

{{eol}}

Data Workbench将用户档案下载到您的计算机。

如果您是首次加载配置文件，则必须具有与 [!DNL Data Workbench server] 并联机工作，以便Data Workbench可以从 [!DNL Data Workbench server].

下载配置文件的过程可能需要几分钟时间。在数据缓存开始填充之前，不要开始使用配置文件，但也不必等到填满。在加载配置文件时，通过查看状态栏，可以跟踪数据缓存的进度、配置文件同步的进度以及最新处理数据的日期和时间。

>[!NOTE]
>
>在数据缓存开始填充之前，您不会在可视化图表中看到所添加的数据。

下次加载配置文件时，只有当您拥有到 [!DNL Data Workbench server] 的网络连接并且联机工作时，才会下载配置文件及其数据的更新。如果您脱机工作，则会从计算机的缓存中加载配置文件及其数据。这种情况下，您查看的配置文件及数据的版本是上次您使用配置文件联机工作时下载的版本。有关联机工作与脱机工作的详细信息，请参阅[脱机工作和联机工作](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54)。

当您需要更改用户档案时(使用 [!DNL Profile Manager] 或 [!DNL Server Files Manager])，则应联机工作以确保具有最新版本的用户档案。 有关 [!DNL Profile Manager] 和 [!DNL Server Files Manager]，请参阅 [管理界面](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

如果您无法访问或加载配置文件，则可能需要确认以下事项：

* 拥有到配置文件所在的 [!DNL Data Workbench server] 计算机的网络连接。
* 拥有访问配置文件的适当权限。

如需帮助，请与您的系统管理员联系。

## 加载或切换用户档案 {#section-c50499d7d8084d7cadfada52df33f5f4}

1. 启动Data Workbench。
1. 在侧栏中，单击配置文件名称，然后单击 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*，其中 *配置文件名称* 是要使用的用户档案。

   ![](assets/sidebar_profile.png)

如果您是首次加载所选择的配置文件，则可能需要几分钟时间才能下载足够的数据来填充可视化。

## 访问群集上的配置文件 {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench在

ata workbench server群集仅标识Data Workbench配置文件( [!DNL Insight.cfg])。 从Data Workbench用户的角度来看，配置文件只能在一个Data Workbench服务器(主控Data Workbench服务器)上访问。 但是，可以将分析师的查询请求定向到群集中的任何Data Workbench服务器。

有关在Data Workbench服务器群集上运行的配置文件的详细信息，请参阅 *《服务器产品安装和管理指南》*.
