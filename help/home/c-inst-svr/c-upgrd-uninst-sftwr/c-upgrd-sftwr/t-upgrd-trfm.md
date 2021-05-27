---
description: 升级转换文件夹的步骤。
title: 升级转换
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# 升级转换{#upgrading-transform}

升级转换文件夹的步骤。

1. 打开[!DNL Insight Server]发行包的[!DNL .zip]文件，然后打开该[!DNL .zip]文件中的[!DNL Profiles]文件夹。
1. 将[!DNL Transform]文件夹复制到[!DNL Insight Server]安装目录的[!DNL Profiles]文件夹中。 这样做会覆盖现有的[!DNL Transform]文件夹。
1. 对于继承[!DNL Transform]配置文件的每个配置文件，确认[!DNL profile.cfg]文件在目录矢量中具有“Transform”条目。
数据重新处理在配置文件同步后开始。
