---
description: 默认情况下，Insight Server将其数据集(temp.db)写入与Insight Server项目文件相同的驱动器。
title: 配置数据集 (temp.db) 的位置
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# 配置数据集 (temp.db) 的位置{#configuring-the-location-of-the-dataset-temp-db}

默认情况下，Insight Server将其数据集(temp.db)写入与Insight Server项目文件相同的驱动器。

例如，如果在驱动器C上安装[!DNL Insight Server]，则数据集将写入驱动器C。

如果您希望[!DNL Insight Server]在其他驱动器上维护数据集，或者您希望收集的数据量需要使用多个驱动器，则必须更新[!DNL Disk Files.cfg]文件以指定[!DNL Insight Server]要写入[!DNL temp.db]文件的位置。

**配置temp.db的位置**

1. 导览至安装[!DNL Insight Server]的目录中的[!DNL Components]文件夹。

   示例：[!DNL C:\Adobe\Server\Components]

1. 在文本编辑器（如记事本）中打开[!DNL Disk Files.cfg]文件。

   默认情况下，此文件在“磁盘文件”结构中包含一个条目，如下所示。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. 要更改[!DNL temp.db]的位置，请修改“Disk Files（磁盘文件）”定义。 以下示例说明了如何编辑配置以跨驱动器C、D和E扩展[!DNL temp.db]文件：

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
   >请注意，在上述文件名中使用了多次反斜杠。 在[!DNL Insight Server]配置文件中，反斜杠字符是转义字符。 它用于在文本中表达特殊的控制序列（例如，\t表示制表符字符）。 要表示实际反斜杠字符，必须键入两次反斜杠（例如，\\）以覆盖转义函数。 仅当在文本编辑器（如记事本）中编辑配置文件时，才适用。
