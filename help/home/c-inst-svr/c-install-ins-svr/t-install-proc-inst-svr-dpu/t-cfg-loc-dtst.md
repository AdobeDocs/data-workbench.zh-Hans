---
description: 默认情况下，Insight Server将其数据集(temp.db)写入与Insight Server项目文件相同的驱动器。
solution: Analytics
title: 配置数据集 (temp.db) 的位置
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---


# 配置数据集 (temp.db) 的位置{#configuring-the-location-of-the-dataset-temp-db}

默认情况下，Insight Server将其数据集(temp.db)写入与Insight Server项目文件相同的驱动器。

例如，如果安装 [!DNL Insight Server] 在驱动器C上，则会将数据集写入驱动器C。

如果要 [!DNL Insight Server] 在其他驱动器上维护数据集，或者要收集的数据量需要使用多个驱动器，则必须更新文件以指定要写入文 [!DNL Disk Files.cfg] 件的位 [!DNL Insight Server][!DNL temp.db] 置。

**配置temp.db的位置**

1. 导览至安 [!DNL Components] 装目录中的文件夹 [!DNL Insight Server]。

   示例：[!DNL C:\Adobe\Server\Components]

1. 在文本 [!DNL Disk Files.cfg] 编辑器（如记事本）中打开文件。

   默认情况下，此文件在“磁盘文件”结构中包含一个条目，如下所示。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. 要更改的位置， [!DNL temp.db]请修改“磁盘文件”定义。 以下示例说明如何编辑配置以将文 [!DNL temp.db] 件跨驱动器C、D和E分布：

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >请注意，在上述文件名中使用多次反斜杠。 在配 [!DNL Insight Server] 置文件中，反斜杠字符是转义字符。 它用于在文本中表达特殊的控制序列（例如，\t表示制表符字符）。 要表示实际的反斜杠字符，必须键入两次反斜杠（例如，\\）以覆盖转义函数。 仅当在文本编辑器（如记事本）中编辑配置文件时，才适用此设置。

