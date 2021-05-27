---
description: 运行Insight Server复制服务的Target Insight Server计算机必须能够读取此中继器服务器上的日志文件。
title: 为目标计算机配置访问控制
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# 为目标计算机配置访问控制{#configuring-access-control-for-target-machines}

运行Insight Server复制服务的Target Insight Server计算机必须能够读取此中继器服务器上的日志文件。

使用[!DNL Access Control.cfg]文件授予对目标计算机的访问权限。

**为目标计算机的访问配置访问控 [!DNL Insight Server] 制**

1. 导航到安装中继器功能的目录中的[!DNL Access Control]文件夹。

   示例：[!DNL D:\Adobe\Repeater\Access Control]

1. 在文本编辑器（如记事本）中打开[!DNL Access Control.cfg]。
1. 为必须访问此中继服务器上日志文件的[!DNL Insight Server]计算机创建访问组。 为此访问组指定一个类似于“复制目标”的名称。

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
   1. 在只读访问部分中，指定复制目标访问的事件数据的位置。 在路径规范(/)中使用正斜杠。 默认位置是中继器计算机(/Logs/)上的[!DNL Logs]文件夹。
   1. 更新只读访问矢量的项目计数，以反映您插入的位置数。

1. 更新文件顶部“访问控制组”矢量中的访问组数量，以反映添加的新访问组。

   ```
   Access Control Groups = vector: n items
   ```

1. 保存文件。
