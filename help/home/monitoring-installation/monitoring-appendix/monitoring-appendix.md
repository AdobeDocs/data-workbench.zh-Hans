---
description: 本文档描述了这些配置文件及其字段、维度和数据工作台监视配置文件所使用的度量。
solution: Analytics
title: 数据工作台配置文件维度和指标
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 数据工作台配置文件维度和指标{#data-workbench-profile-dimensions-and-metrics}

本文档描述了这些配置文件及其字段、维度和数据工作台监视配置文件所使用的度量。

要监视数据工作台服务器，数据会使用一个脚本来收集，该脚本可分析“详细状态”并捕获特定服务器信息。 然后，Data Workbench Server信息会传递到页面标记调用，以便Data Workbench Sensor收集并保存到VSL文件。

## 数据工作台监视配置文件使用的配置文件 {#section-b5b1234f55c3407dae8e68b031b7cd7f}

这些配置文件提供了允许您查看服务器状态和性能数据的维度和指标：

* [Insight配置文件状态配置文件中的维](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Insight Server状态配置文件中的维](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Insight Historic配置文件中的维](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Insight Historical Monitoring配置文件中的指标](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

状态配置文件允许您从操作角度查看数据工作台当前的执行情况。 配置 **文件状态配置文件和** “服务器状态”配置 **** 文件会从“详细状态”和“数据工作台”服务器收集数据。 收集的所有数据都会放入字段 `cs-uri-query` 中以供使用。

历史 **配置文件** ，允许您使用历史数据评估配置和硬件更改的影响。 历史配置文件可能最有用，因为它允许您评估配置和硬件更改随时间的变化的影响。
