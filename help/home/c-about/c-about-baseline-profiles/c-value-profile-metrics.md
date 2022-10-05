---
description: 值配置文件量度
title: 值配置文件量度
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# 值配置文件量度{#value-profile-metrics}

{{eol}}

| 量度 | 公式 | 级别 | 描述 |
|---|---|---|---|
| 转化 | `Sessions[not Session_Value=#0]/Sessions` | 会话 | 产生业务价值的会话的百分比（由业务价值模型定义）。 |
| 值百分比 | `Value/total(Value)` | 会话 | 从选定的会话集生成的总值的百分比。 |
| 值 | `sum(Session_Value, Session)*0.01` | 会话 | 生成的总业务价值（以美元为单位，由业务价值模型定义）。 |
| 值事件 | `Sessions[not Session_Value=#0]` | 会话 | 产生业务价值的会话计数（由业务价值模型定义）。 |
| 每位访客的值事件 | `(Value_Events/Visitors) by Visitor` | 访客 | 每个访客产生业务价值的平均会话数（由业务价值模型定义）。 |
| 每位访客的值 | `(Value/Visitors) by Visitor` | 访客 | 每位访客产生的平均业务价值（以美元为单位）。 |
