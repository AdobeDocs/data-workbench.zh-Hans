---
description: 有关将visual_sciences.dll添加到Tomcat Java库路径的说明。
title: 修改Java库路径
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改Java库路径{#modify-the-java-library-path}

有关将visual_sciences.dll添加到Tomcat Java库路径的说明。

1. 在Windows服务器上，导航到Tomcat安装目录。 (Tomcat > bin)
1. 在bin文件夹下，运行Tomcat9w.exe（常见守护程序服务管理器）。

在Java选项卡的Java选项下，添加新行：

```
-Djava.library.path=C:\Sensor directory
```

其中C:\Sensor directory is the directory containing the visual_sciences.dll文件。
