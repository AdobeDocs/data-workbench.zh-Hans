---
description: 要更彻底地监控实施，您可以监控服务器计算机上的所有端口以及这些端口上运行的软件产品。
solution: Insight
title: 监视端口和应用程序
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 监视端口和应用程序{#monitoring-ports-and-applications}

要更彻底地监控实施，您可以监控服务器计算机上的所有端口以及这些端口上运行的软件产品。

**推荐频率：** 每5-10分钟

使用应用程序或脚本，您可以监视每个应用程序所运行的TCP端口（通常为端口80或443），以确保应用程序绑定到该端口。 为此，您从要监视的计算机请求应用程序状态页。

**请求应用程序状态页**

1. 在要监视的计算机上，修改访问控制以允许监视应用程序或脚本访问计算机。 有关说明，请参阅 [配置访问控制](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。
1. 连接 [!DNL https://IP Address/Status/]到，其中IP地址是要接收其状态的计算机的IP地址。

   示例：[!DNL https://127.0.0.1/Status/]

   计算机应以服务器状态描述进行响应。 如果它未响应，请检查您的活动日志并联系Adobe客户服务。

   有关此类高级监控的详细信息，请与Adobe咨询服务部门联系。

