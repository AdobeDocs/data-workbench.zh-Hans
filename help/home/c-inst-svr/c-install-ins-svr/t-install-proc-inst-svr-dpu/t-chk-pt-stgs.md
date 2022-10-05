---
description: 默认情况下， Insight Server监听端口80（对于HTTP）和443（对于HTTPS）。
title: 检查端口设置
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# 检查端口设置{#checking-the-port-settings}

{{eol}}

默认情况下， Insight Server监听端口80（对于HTTP）和443（对于HTTPS）。

如果这些端口已经由安装计算机上的其他进程分配 [!DNL Insight Server]，请按照以下过程进行更改 [!DNL Insight Server’s] 端口分配。

**更改端口分配**

1. 导航到 [!DNL Components] 文件夹。 [!DNL Insight Server].

   示例：[!DNL C:\Adobe\Server\Components]

1. 打开 [!DNL Communications.cfg] 文件（如记事本）。
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

1. 如果这些端口不是您想要的端口 [!DNL Insight Server] 要使用，请更改端口分配，然后保存并关闭文件。
