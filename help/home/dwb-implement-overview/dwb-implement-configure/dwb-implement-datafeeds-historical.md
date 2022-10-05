---
description: 有关验证和设置历史数据馈送所需的最低步骤的快速指南。
title: 验证历史数据馈送
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# 验证历史数据馈送{#validating-historical-data-feeds}

{{eol}}

有关验证和设置历史数据馈送所需的最低步骤的快速指南。

## 验证数据馈送一致性的步骤 {#section-777b2c627a354627a02feb9461e23038}

1. 登录 *牙齿* (https://oasis.omniture.com/drteeth/)
1. 转到SiteCatalyst管理员 — >数据馈送定义（新）
1. 跳转到服务器位置(例如 达拉斯，伦敦……) 具体取决于贵组织所在的位置。
1. 提供RSID并选择信息源类型Insight并单击 *搜索*.

   ![](assets/dwb_impl_historical.png)

1. 确定客户端的实际馈送名称。
1. 单击“操作”部分中的“历史记录”。 ![](assets/dwb_impl_historical1.png)

   检查状态字段中是否存在任何错误。如果某些馈送处于错误状态，请选择该馈送，然后单击重新处理。 如果多个请求出错，则发送电子邮件至 *`dataworkbench@adobe.com`* 和报表包详细信息，以便重新处理。

1. 验证后会检查NAS位置原始文件夹中的日志。
