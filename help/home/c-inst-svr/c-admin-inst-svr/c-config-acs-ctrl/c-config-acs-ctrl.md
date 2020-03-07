---
description: 访问控制配置文件Access Control.cfg定义访问控制组，Insight Server通过这些访问控制组根据传入连接证书的属性（OU、CN等）为文件授予权限。
solution: Insight
title: 配置访问控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置访问控制{#configuring-access-control}

访问控制配置文件Access Control.cfg定义访问控制组，Insight Server通过这些访问控制组根据传入连接证书的属性（OU、CN等）为文件授予权限。

**推荐频率：** 根据需要

[!DNL Insight Server] 提供可配置的访问控制组，以管理与的连接的安全性 [!DNL Insight Server]。 访问控制组识别允许通过执行管理功能的用户 [!DNL Insight]。

如果需要向新用户或新计算机提供访问权限（例如向群集添加计算机时），您只需 [!DNL Insight Server] 编辑访问控制配置文件。
