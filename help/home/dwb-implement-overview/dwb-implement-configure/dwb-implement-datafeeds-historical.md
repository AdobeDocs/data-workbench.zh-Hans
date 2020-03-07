---
description: 快速指南，了解验证和设置历史数据源所需的最低步骤。
title: 验证历史数据源
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 验证历史数据源{#validating-historical-data-feeds}

快速指南，了解验证和设置历史数据源所需的最低步骤。

## 数据馈送一致性的验证步骤 {#section-777b2c627a354627a02feb9461e23038}

1. 登录 *到dreth* (https://oasis.omniture.com/drteeth/)
1. 转至SiteCatalyst管理员->数据源定义（新）
1. 跳转至服务器位置(例如 达拉斯，伦敦……)具体取决于您所在的单位。
1. 提供RSID并选择源类型Insight，然后单击搜 *索*。

   ![](assets/dwb_impl_historical.png)

1. 确定客户的实际源名称。
1. 单击“操作”部分中的“历史记录”。 ![](assets/dwb_impl_historical1.png)

   检查状态字段是否有任何错误，如果某些源处于错误状态，请选择该源并单击重新处理。 如果多个请求发生错误，请发送一封电子邮件至，其 *`dataworkbench@adobe.com`* 中包含源ID和报告包详细信息以重新处理。

1. 验证后会检查NAS位置原始文件夹中的日志。

