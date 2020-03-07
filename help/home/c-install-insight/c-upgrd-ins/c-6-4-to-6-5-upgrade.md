---
description: 按照这些步骤升级至 Data Workbench v6.5。
title: 将 6.4 升级至 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 将 6.4 升级至 6.5{#upgrading-to}

按照这些步骤升级至 Data Workbench v6.5。

## 升级要求和建议 {#section-8704a9ac358246cd81233dd0982d534f}

请在升级到 Data Workbench 6.5 时，遵循下面的要求和建议。

* Changes in the **[!DNL Components for Processing Servers\Communications.cfg]** file require you to update this file for the DWB 6.5 release. *SourceListServer*、*SegmentExportServer* 和 *NormalizeServer* 条目已删除。（DPU 不应运行 *sourcelist*、*segment export* 或 *normalize servers*。）

* 关联和弦、关联矩阵、联合和弦、联合矩阵、倾向得分和最适合归因可视化当前为多次传递可视化。

   当工作区存在多个多次传递可视化时，报表服务器在默认情况下将无法生成报表，并显示错误：

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   通过更新 [!DNL ReportServer.cfg] 文件，或将此行添加到现有文件中的 *Reporting* 部分，可避免此错误。

   ```
   Max Multipass Per Slice = int: n
   ```

   其中，n 为 Report Server 在工作区内支持多次传递可视化的最大数量。

