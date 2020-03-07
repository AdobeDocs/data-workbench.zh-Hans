---
description: 默认情况下，Insight Server监听端口80（对于HTTP）和443（对于HTTPS）。
solution: Insight
title: 检查端口设置
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 检查端口设置{#checking-the-port-settings}

默认情况下，Insight Server监听端口80（对于HTTP）和443（对于HTTPS）。

如果这些端口已经由安装了的计算机上的其他进程分配，请 [!DNL Insight Server]按照以下过程更改端 [!DNL Insight Server’s] 口分配。

**更改端口分配**

1. 导览至您 [!DNL Components] 所安装目录中的文件夹 [!DNL Insight Server]。

   示例：[!DNL C:\Adobe\Server\Components]

1. 在文本 [!DNL Communications.cfg] 编辑器（如记事本）中打开文件。
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

1. 如果这些端口不是您要使用的端 [!DNL Insight Server] 口，请更改端口分配，然后保存并关闭文件。
