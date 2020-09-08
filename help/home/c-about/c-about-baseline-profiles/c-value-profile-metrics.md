---
description: 'null'
solution: Analytics
title: 值配置文件量度
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 16%

---


# 值配置文件量度{#value-profile-metrics}

| 量度 | 公式 | 级别 | 描述 |
|---|---|---|---|
| 转化 | `Sessions[not Session_Value=#0]/Sessions` | 会话 | 产生业务价值的会话百分比（由业务价值模型定义）。 |
| 值百分比 | `Value/total(Value)` | 会话 | 从所选会话集生成的总值的百分比。 |
| 值 | `sum(Session_Value, Session)*0.01` | 会话 | 生成的业务价值总额（以美元为单位，由业务价值模型定义）。 |
| 价值事件 | `Sessions[not Session_Value=#0]` | 会话 | 生成业务价值的会话计数（由业务价值模型定义）。 |
| 每访客的价值事件 | `(Value_Events/Visitors) by Visitor` | 访客 | 产生业务价值的每个访客的平均会话数（由业务价值模型定义）。 |
| 每访客值 | `(Value/Visitors) by Visitor` | 访客 | 每个访客产生的平均业务价值（以美元为单位）。 |
