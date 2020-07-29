---
description: 目标运行Insight Server复制服务的Insight Server计算机必须能够读取此中继服务器上的日志文件。
solution: Insight
title: 为目标计算机配置访问控制
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: 0276701151d1403926ce184069526ebdf3e28e36
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---


# 为目标计算机配置访问控制{#configuring-access-control-for-target-machines}

目标运行Insight Server复制服务的Insight Server计算机必须能够读取此中继服务器上的日志文件。

使用文件授予对目标机的访 [!DNL Access Control.cfg] 问权。

**配置访问控制以通过目标机访[!DNL Insight Server]问**

1. 导览至您 [!DNL Access Control] 安装了repeater功能的目录中的文件夹。

   示例：[!DNL D:\Adobe\Repeater\Access Control]

1. 在文 [!DNL Access Control.cfg] 本编辑器（如记事本）中打开。
1. 为必须访问此转发器服 [!DNL Insight Server] 务器上日志文件的计算机创建访问组。 为此访问组命名类似“复制目标”。

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

   1. 在“成员”部分，指定每台计算机的IP地址。
   1. 更新“成员”矢量的项计数，以反映您插入的计算机IP地址数。
   1. 在“只读访问”部分，指定复制目标访问的事件数据的位置。 在路径规范(/)中使用正斜杠。 默认位置是 [!DNL Logs] Repeater计算机(/Logs/)上的文件夹。
   1. 更新只读访问矢量的项目计数以反映您插入的位置数。

1. 更新文件顶部“访问控制组”矢量中的访问组数，以反映新访问组的添加。

   ```
   Access Control Groups = vector: n items
   ```

1. 保存文件。
