---
description: 下面列出了Data Workbench历史监控配置文件中包含的量度及其派生方式。
title: Data Workbench 历史监控配置文件中的量度
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Data Workbench 历史监控配置文件中的量度{#metrics-in-the-data-workbench-historical-monitoring-profile}

{{eol}}

下面列出了Data Workbench历史监控配置文件中包含的量度及其派生方式。

| **警报标准** | 每个Ping的“警报关键”维度的总和。 |
|---|---|
| **警报关闭** | 每个Ping的“向下警报”维度的总和。 |
| **警报警告** | 每个Ping的“警报警告”维度的总和。 |
| **所有组件** | 组件检查成功等于“1”的Ping计数除以Ping量度乘以100。 |
| **截止延迟分钟数** | 此量度是每个Ping的截止延迟分钟数之和，然后除以Ping量度。 |
| **块** | 每个块的总和。 |
| **全部阻止** | 所有区块。 |
| **总体容量** | 容量大小量度乘以2，再加上容量行量度除以3。 |
| **容量行** | 每个Ping的“容量行百分比”维度的总和除以Ping量度。 |
| **容量大小** | 每个Ping的“容量大小百分比”维度的总和除以Ping量度。 |
| **通信** | 快速检查成功与“1”匹配的Ping次数，除以Ping量度。 |
| **详细检查秒数** | 每个Ping的详细检查秒数维度的总和，其中Ping类型为“服务器”，除以Ping量度。 |
| **DimensionGigaBytes** | 每个Ping的DimensionGB总和除以Ping量度。 |
| **磁盘&quot;x&quot;** | 磁盘量度的计算方式是：计算每个Ping的磁盘使用百分比之和，再除以Ping量度。 |
| **估计扫描分钟数** | 这是每个Ping的估计扫描除数的总和，除以Ping量度，其中估计扫描除数大于零，全部除以6。 |
| **每分钟快速输入MB** | 每个Ping的快速输入兆字节/分钟总和除以当快速输入兆字节/分钟大于零时的Ping数。 |
| **快速输入模式** | 处理模式维度等于“快速输入”除以Ping的Ping。 |
| **每分钟快速合并MegaBytes** | 每个Ping的快速合并兆字节/分钟总和除以Ping量度。 |
| **快速合并模式** | 处理模式等于“快速合并”除以Ping量度的Ping。 |
| **字段GigaBytes** | 每个Ping的字段GB维度总和除以Ping量度。 |
| **加载** | 每个Ping的“平均加载次数”维度的总和除以Ping量度。 |
| **日志读取** | 每个Ping的日志读取处理维度的总和除以Ping量度，总和除以10。 |
| **内存页** | 每个Ping的内存页文件百分比总和除以Ping量度。 |
| **内存物理** | 每个Ping的“内存物理百分比”维度的总和除以Ping量度。 |
| **内存查询** | 每个Ping的内存查询百分比总和除以Ping量度。 |
| **总内存GB** | 每个Ping的内存物理MegaBytes总维度的总和除以Ping量度。 |
| **网络连接** | 这是每个Ping的网络连接总和除以Ping量度。 |
| **Ping x总容量** | Ping量度乘以总容量量度。 |
| **投票延迟毫秒数** | 每个Ping的“投票延迟厘秒”维度的总和，除以Ping量度，总和乘以10。 |
| **查询正在运行** | 每个Ping的总和，其中估计扫描秒数大于“0”，除以Ping类型等于“server”的Ping量度。 |
| **快速检查秒数** | 每个Ping的快速检查秒数之和，其中Ping类型等于“服务器”，除以Ping量度。 |
| **输出行** | 每个ping的“输出行”维度的总和除以Ping量度，再乘以100000。 |
| **实时模式** | 处理模式维度等于“实时”的Ping次数，除以Ping量度，然后全部乘以100。 |
| **重新处理模式** | 100减去处理模式等于“实时”的Ping数除以Ping量度，再乘以100。 |
| **停滞** | Insight中处理停止维度的总和 [用户档案状态](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) 配置文件。 |
| **临时数据库** | 每个Ping的临时数据库空间百分比之和除以Ping量度。 |
| **转换** | 每个Ping的转换百分比总和除以Ping量度，总和除以10。 |
