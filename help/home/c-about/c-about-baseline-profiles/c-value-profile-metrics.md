---
description: 'null'
solution: Analytics
title: 价值档案指标
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 价值档案指标{#value-profile-metrics}

| 量度 | 公式 | 级别 | 描述 |
|---|---|---|---|
| 转化 | [!DNL会[话不是Session_Value=#0]/Sessions] | 会话 | 产生业务价值的会话百分比（由业务价值模型定义）。 |
| 值百分比 | [!DNL Value/total(Value)] | 会话 | 从所选会话集生成的总值百分比。 |
| 值 | [!DNL sum(Session_Value, Session)*0.01] | 会话 | 生成的总业务价值（以美元为单位）（由“业务价值模型”定义）。 |
| 价值事件 | [!DNL会[话不是Session_Value=#0]] | 会话 | 产生业务价值的会话计数（由业务价值模型定义）。 |
| 每位访客的价值事件 | [!DNL (Value_Events/Visitors) by Visitor] | 访客 | 产生业务价值的每个访客的平均会话数（由业务价值模型定义）。 |
| 每位访客的价值 | [!DNL (Value/Visitors) by Visitor] | 访客 | 每位访客产生的平均业务价值（以美元为单位）。 |
