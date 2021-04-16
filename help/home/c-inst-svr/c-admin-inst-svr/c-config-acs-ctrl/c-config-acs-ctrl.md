---
description: 访问控制配置文件访问控制.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）授予文件权限。
title: 配置访问控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# 配置访问控制{#configuring-access-control}

访问控制配置文件访问控制.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）授予文件权限。

**推荐频率：** 根据需要

[!DNL Insight Server] 提供可配置的访问控制组，以管理与的连接的安全 [!DNL Insight Server]性。访问控制组标识允许通过[!DNL Insight]执行管理功能的用户。

如果需要向新用户或新计算机提供访问权限，例如向[!DNL Insight Server]群集添加计算机时，只需编辑访问控制配置文件。
