---
description: 仪表板要从中可视化数据的每个DPU都必须具有Query API许可证。
solution: Analytics
title: 验证查询API启用
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 验证查询API启用{#verifying-query-api-enablement}

仪表板要从中可视化数据的每个DPU都必须具有Query API许可证。

下面是有关如何验证已安装并启用Query API的一些说明。

1. 查找您的Data Workbench Server的证书。
1. 在文本编辑器中打开此证书。
1. 确保该行存 `Product = Query API` 在于证书中。
1. 在文 **[!UICONTROL Trace]** 件夹中，在文本 [!DNL InsightServer64.log] 编辑器中打开。
1. 在最新的启动日志条目中，确保显示该 `Enabling Query API (licensed)` 行。

* 如果未启用查询API，您将看到该条目 `Not enabling Query API (not licensed)`。
* 如果未看到任何日志条目，或怀疑添加Query API后已重新启动Data Workbench Server，请再次重新启动Data Workbench Server，并检查日志。

   如果您无法验证是否已启用查询API，请联系Adobe ClientCare寻求帮助。
