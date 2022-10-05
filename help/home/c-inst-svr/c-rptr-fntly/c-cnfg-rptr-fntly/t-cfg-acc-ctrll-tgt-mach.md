---
description: 运行Insight Server复制服务的Target Insight Server计算机必须能够读取此中继器服务器上的日志文件。
title: 为目标计算机配置访问控制
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# 为目标计算机配置访问控制{#configuring-access-control-for-target-machines}

{{eol}}

运行Insight Server复制服务的Target Insight Server计算机必须能够读取此中继器服务器上的日志文件。

使用 [!DNL Access Control.cfg] 文件。

**配置访问控制以便由目标访问 [!DNL Insight Server] 机器**

1. 导航到 [!DNL Access Control] 文件夹。

   示例：[!DNL D:\Adobe\Repeater\Access Control]

1. 打开 [!DNL Access Control.cfg] 在文本编辑器（如记事本）中。
1. 为 [!DNL Insight Server] 必须访问此中继服务器上日志文件的计算机。 为此访问组指定一个类似于“复制目标”的名称。

   以下文件片段显示访问组的外观。

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. 在成员部分，指定每台计算机的IP地址。
   1. 更新“成员”矢量的项目计数，以反映您插入的计算机IP地址数。
   1. 在只读访问部分中，指定复制目标访问的事件数据的位置。 在路径规范(/)中使用正斜杠。 默认位置为 [!DNL Logs] 文件夹(/Logs/)。
   1. 更新只读访问矢量的项目计数，以反映您插入的位置数。

1. 更新文件顶部“访问控制组”矢量中的访问组数量，以反映添加的新访问组。

   ```
   Access Control Groups = vector: n items
   ```

1. 保存文件。
