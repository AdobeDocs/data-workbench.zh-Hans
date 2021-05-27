---
description: 功能板要从中可视化数据的每个DPU都必须具有查询API许可证。
title: 验证查询 API 是否启用
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# 验证查询 API 是否启用{#verifying-query-api-enablement}

功能板要从中可视化数据的每个DPU都必须具有查询API许可证。

以下是有关如何验证是否已安装并启用查询API的说明。

1. 查找Data Workbench Server的证书。
1. 在文本编辑器中打开此证书。
1. 确保证书中存在行`Product = Query API`。
1. 在&#x200B;**[!UICONTROL Trace]**&#x200B;文件夹中，在文本编辑器中打开[!DNL InsightServer64.log]。
1. 在最新的启动日志条目中，确保出现`Enabling Query API (licensed)`行。

* 如果未启用查询API，您将看到`Not enabling Query API (not licensed)`条目。
* 如果您没有看到任何日志条目，或者怀疑自添加查询API以来已重新启动Data Workbench Server，请再次重新启动Data Workbench Server，然后检查日志。

   如果您无法验证查询API是否已启用，请联系AdobeClientCare以寻求帮助。
