---
description: 必须每天使用贵公司的正常备份系统和灾难恢复程序备份事件数据。
title: 备份事件数据
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# 备份事件数据{#backing-up-event-data}

{{eol}}

必须每天使用贵公司的正常备份系统和灾难恢复程序备份事件数据。

**推荐频率：** 每日

[!DNL Insight Server] 每天中午12:00（格林威治标准时间）开始新的日志文件。 Adobe建议您在格林威治标准时间午夜12:00后不久每天备份日志文件，以便捕获前一天的所有数据。 例如，在格林尼治时间12月15日凌晨12:05备份所有日志文件将捕获12月14日起的所有数据。 [!DNL Insight Server] 在日志文件备份期间不需要停止，并且所有功能都仍然可用。

## 备份集成、操作系统、输出和系统数据 {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**推荐频率：** 每日

必须使用您公司的常规备份和灾难恢复系统定期并认真备份集成、操作系统、输出和系统数据。
