---
description: 升级Transform文件夹的步骤。
solution: Analytics
title: 升级转换
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---


# 升级转换{#upgrading-transform}

升级Transform文件夹的步骤。

1. 打开发 [!DNL .zip] 行包的文 [!DNL Insight Server] 件，并打开该文 [!DNL Profiles] 件中的文 [!DNL .zip] 件夹。
1. 将文件夹 [!DNL Transform] 复制到安 [!DNL Profiles] 装目录中的 [!DNL Insight Server] 文件夹中。 这样做会覆盖现有文 [!DNL Transform] 件夹。
1. 对于继承该用户档案的 [!DNL Transform] 每个用户档案，确 [!DNL profile.cfg] 认该文件在“目录”矢量中有一个“转换”条目。
用户档案同步后，数据重新处理开始。
