---
description: 以下列表了Data Workbench历史监视用户档案中包含的量度及其派生方式。
title: Data Workbench 历史监控配置文件中的量度
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Data Workbench 历史监控配置文件中的量度{#metrics-in-the-data-workbench-historical-monitoring-profile}

以下列表了Data Workbench历史监视用户档案中包含的量度及其派生方式。

| **警告** | 每个Ping的“严重警报”维度的总和。 |
|---|---|
| **警报下载** | 每个Ping的Alert Down维度的总和。 |
| **警报警告** | 每个Ping的警报警告维度的总和。 |
| **所有组件** | 组件检查成功等于“1”的Ping计数除以Ping量度乘以100。 |
| **截至延迟分钟** | 此量度是每个Ping的延迟分钟数的总和，然后除以Ping量度。 |
| **块** | 每个块的1的和。 |
| **全部阻止** | 所有区块。 |
| **总体容量** | 容量大小量度乘以2加上容量行量度，除以3。 |
| **容量行** | 每个Ping的“容量行百分比”维度的总和除以Ping量度。 |
| **容量大小** | 每个Ping的“容量大小百分比”维度的总和，除以Ping量度。 |
| **通信** | 快速检查成功与“1”匹配的Ping数，除以Ping量度。 |
| **详细检查秒数** | 每个Ping的详细检查秒数维度的总和，其中ping类型为“服务器”，除以Ping量度。 |
| **Dimension GigaBytes** | 每个Ping的DimensionGB总和，除以Ping量度。 |
| **磁盘&quot;x&quot;** | 磁盘量度的计算方法是：取每个Ping的磁盘使用百分比之和除以Ping量度。 |
| **估计扫描分钟数** | 这是每个Ping的估计扫描秒数之和，除以估计扫描秒数大于零的Ping量度，全部除以6。 |
| **每分钟快速输入MB** | 每个Ping的快速输入兆字节/分钟总和除以当快速输入兆字节/分钟大于零时的Ping数。 |
| **快速输入模式** | Ping ，其中处理模式维度等于“快速输入”除以Ping。 |
| **每分钟快速合并兆字节** | 每个Ping的快速合并兆字节/分钟总和，除以Ping量度。 |
| **快速合并模式** | 在Ping中，处理模式等于“快速合并”除以Ping量度。 |
| **字段GigaBytes** | 每个Ping的字段GB维度之和除以Ping量度。 |
| **加载** | 每个Ping的“负载平均”维的和，除以Ping量度。 |
| **日志读取** | 每个Ping的日志读取处理维度的和，除以Ping量度，全部除以10。 |
| **内存页** | 每个Ping的“内存页文件百分比”除以Ping量度之和。 |
| **内存物理** | 每个Ping的“内存物理百分比”维度的总和，除以Ping量度。 |
| **内存查询** | 每个Ping的内存查询百分比之和，除以Ping量度。 |
| **总内存GB** | 每个Ping的内存物理MegaBytes总维度的和，除以Ping量度。 |
| **网络连接** | 这是每个Ping的网络连接总和除以Ping量度。 |
| **Ping X总容量** | Ping量度乘以总容量量度。 |
| **轮询延迟毫秒** | 每个Ping的轮询延迟厘秒维度的总和，除以Ping量度，全部乘以10。 |
| **查询运行** | 每个Ping的1之和，其中估计的扫描数大于“0”，除以Ping类型等于“服务器”的Ping量度。 |
| **快速检查秒数** | 每个Ping的快速检查秒数之和，其中Ping类型等于“服务器”，除以Ping量度。 |
| **输出行** | 每个ping的输出行维度之和除以Ping量度，再乘以100000。 |
| **实时模式** | 处理模式维度等于“实时”的Ping数，除以Ping量度，全部乘以100。 |
| **重新处理模式** | 100减去处理模式等于“实时”的Ping数，再除以Ping量度，再乘以100。 |
| **停滞** | Insight [用户档案状态](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)用户档案中处理停止维度的总和。 |
| **临时数据库** | 每个Ping的临时数据库空间百分比之和，除以Ping量度。 |
| **转换** | 每个Ping的转换百分比之和除以Ping量度，全部除以10。 |
