---
description: 有关将visual_sciences.dll添加到Tomcat Java库路径的说明。
title: 修改 Java 库路径
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# 修改 Java 库路径{#modify-the-java-library-path}

{{eol}}

有关将visual_sciences.dll添加到Tomcat Java库路径的说明。

1. 在Windows服务器上，导航到Tomcat安装目录。 (Tomcat > bin)
1. 在bin文件夹下，运行Tomcat9w.exe（常用守护程序服务管理器）。

在Java选项卡的Java选项下，添加新行：

```
-Djava.library.path=C:\Sensor directory
```

其中C:\Sensor directory is the directory containing the visual_sciences.dll文件。
