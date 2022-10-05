---
description: 升级转换文件夹的步骤。
title: 升级转换
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# 升级转换{#upgrading-transform}

{{eol}}

升级转换文件夹的步骤。

1. 打开 [!DNL .zip] 文件 [!DNL Insight Server] 版本包，然后打开 [!DNL Profiles] 文件夹 [!DNL .zip] 文件。
1. 复制 [!DNL Transform] 文件夹 [!DNL Profiles] 文件夹中 [!DNL Insight Server] 安装目录。 此操作会覆盖现有 [!DNL Transform] 文件夹。
1. 对于继承 [!DNL Transform] 配置文件，确认 [!DNL profile.cfg] 文件在目录矢量中具有“转换”条目。
数据重新处理在配置文件同步后开始。
