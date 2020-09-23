---
description: 访问控制配置文件访问控制.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）为文件授予权限。
solution: Analytics
title: 配置访问控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---


# 配置访问控制{#configuring-access-control}

访问控制配置文件访问控制.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）为文件授予权限。

**推荐频率：** 根据需要

[!DNL Insight Server] 提供可配置的访问控制组，以管理连接的安全性 [!DNL Insight Server]。 访问控制组识别允许通过执行管理功能的用户 [!DNL Insight]。

如果需要向新用户或新计算机提供访问权限（如向群集添加计算机时）, [!DNL Insight Server] 只需编辑访问控制配置文件。
