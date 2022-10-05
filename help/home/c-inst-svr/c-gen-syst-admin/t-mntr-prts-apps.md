---
description: 要更彻底地监控您的实施，您可以监控服务器计算机上的所有端口以及这些端口上运行的软件产品。
title: 监控端口和应用程序
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# 监控端口和应用程序{#monitoring-ports-and-applications}

{{eol}}

要更彻底地监控您的实施，您可以监控服务器计算机上的所有端口以及这些端口上运行的软件产品。

**推荐频率：** 每5-10分钟

使用应用程序或脚本，可以监视每个应用程序运行的TCP端口（通常为端口80或443），以确保应用程序绑定到该端口。 为此，您需要从要监视的计算机请求应用程序状态页。

**请求应用程序状态页**

1. 在要监视的计算机上，修改访问控制以允许监视应用程序或脚本访问该计算机。 有关说明，请参阅 [配置访问控制](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. 连接到 [!DNL https://IP Address/Status/]，其中IP地址是要接收状态的计算机的IP地址。

   示例：[!DNL https://127.0.0.1/Status/]

   计算机应使用服务器状态描述做出响应。 如果它未做出响应，请检查您的事件日志并联系Adobe客户关怀团队。

   有关此类高级监控的更多信息，请联系Adobe咨询服务。
