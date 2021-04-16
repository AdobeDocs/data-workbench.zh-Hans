---
description: 默认情况下，Insight Server监听端口80（对于HTTP）和443（对于HTTPS）。
title: 检查端口设置
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# 检查端口设置{#checking-the-port-settings}

默认情况下，Insight Server监听端口80（对于HTTP）和443（对于HTTPS）。

如果这些端口已经由安装[!DNL Insight Server]的计算机上的其他进程分配，请使用以下过程更改[!DNL Insight Server’s]端口分配。

**更改端口分配**

1. 导览至安装[!DNL Insight Server]的目录中的[!DNL Components]文件夹。

   示例：[!DNL C:\Adobe\Server\Components]

1. 在文本编辑器（如记事本）中打开[!DNL Communications.cfg]文件。
1. 找到端口和SSL端口条目，如下所示：

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. 如果这些端口不是您希望[!DNL Insight Server]使用的端口，请更改端口分配，然后保存并关闭文件。
