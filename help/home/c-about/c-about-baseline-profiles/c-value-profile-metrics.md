---
description: 值配置文件量度
title: 值配置文件量度
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# 值配置文件量度{#value-profile-metrics}

| 指标 | 公式 | 级别 | 描述 |
|---|---|---|---|
| 转化 | `Sessions[not Session_Value=#0]/Sessions` | 会话 | 生成业务价值（由业务价值模型定义）的会话的百分比。 |
| 值百分比 | `Value/total(Value)` | 会话 | 从所选会话集生成的总值的百分比。 |
| 值 | `sum(Session_Value, Session)*0.01` | 会话 | 生成的业务价值总额（以美元为单位，由业务价值模型定义）。 |
| 价值事件 | `Sessions[not Session_Value=#0]` | 会话 | 生成业务价值（由业务价值模型定义）的会话计数。 |
| 每个事件的价值 | `(Value_Events/Visitors) by Visitor` | 访客 | 产生业务价值的每个访客（由业务价值模型定义）的平均会话数。 |
| 每访客值 | `(Value/Visitors) by Visitor` | 访客 | 每个访客产生的平均业务价值（以美元为单位）。 |
