---
description: 访问控制配置文件Access Control.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）授予文件权限。
title: 配置访问控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# 配置访问控制{#configuring-access-control}

{{eol}}

访问控制配置文件Access Control.cfg定义访问控制组，Insight Server通过这些组根据传入连接证书的属性（OU、CN等）授予文件权限。

**推荐频率：** 根据需要

[!DNL Insight Server] 提供可配置的访问控制组，以管理与 [!DNL Insight Server]. 访问控制组识别允许通过 [!DNL Insight].

如果您需要为新用户或新计算机提供访问权限，例如在将计算机添加到 [!DNL Insight Server] 群集时，您只需编辑访问控制配置文件即可。
