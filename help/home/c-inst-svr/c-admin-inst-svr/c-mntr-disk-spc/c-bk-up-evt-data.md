---
description: 必须使用公司的常规备份系统和灾难恢复过程每天备份事件数据。
solution: Insight
title: 备份事件数据
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 备份事件数据{#backing-up-event-data}

必须使用公司的常规备份系统和灾难恢复过程每天备份事件数据。

**推荐频率：** 每日

[!DNL Insight Server] 每天格林尼治时间凌晨12:00开始新的日志文件。 Adobe建议您每天在格林尼治时间凌晨12:00之后不久备份日志文件，以便捕获前一天的所有数据。 例如，在12月15日格林尼治时间凌晨12:05备份所有日志文件将捕获12月14日的所有数据。 [!DNL Insight Server] 在日志文件备份过程中不需要停止，并且所有功能都保持可用。

## 备份集成、操作系统、输出和系统数据 {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**推荐频率：** 每日

必须使用公司的常规备份和灾难恢复系统定期、认真地备份集成、操作系统、输出和系统数据。
