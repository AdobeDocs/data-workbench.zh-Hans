---
description: 访问控制配置文件Access Control.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）授予文件权限。
title: 配置访问控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# 配置访问控制{#configuring-access-control}

访问控制配置文件Access Control.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）授予文件权限。

**推荐频度：** 根据需要

[!DNL Insight Server] 提供可配置的访问控制组，以管理与的连接的安 [!DNL Insight Server]全性。访问控制组识别允许通过[!DNL Insight]执行管理功能的用户。

如果需要为新用户或新计算机提供访问权限，例如在将计算机添加到[!DNL Insight Server]群集时，只需编辑Access Control配置文件。
