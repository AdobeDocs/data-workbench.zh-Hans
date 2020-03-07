---
description: 升级Transform文件夹的步骤。
solution: Insight
title: 升级转换
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 升级转换{#upgrading-transform}

升级Transform文件夹的步骤。

1. 打开发 [!DNL .zip] 行包的文 [!DNL Insight Server] 件，并打开该文件 [!DNL Profiles] 中的文件 [!DNL .zip] 夹。
1. 将文件 [!DNL Transform] 夹复制到安 [!DNL Profiles] 装目录中 [!DNL Insight Server] 的文件夹。 这样做会覆盖现有的文 [!DNL Transform] 件夹。
1. 对于继承配置文件的每 [!DNL Transform] 个配置文件，确认 [!DNL profile.cfg] 该文件在“目录”矢量中有一个“转换”条目。
数据重新处理在配置文件同步后开始。
