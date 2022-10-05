---
description: 默认情况下， Insight Server将其数据集(temp.db)写入与Insight Server程序文件相同的驱动器。
title: 配置数据集 (temp.db) 的位置
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# 配置数据集 (temp.db) 的位置{#configuring-the-location-of-the-dataset-temp-db}

{{eol}}

默认情况下， Insight Server将其数据集(temp.db)写入与Insight Server程序文件相同的驱动器。

例如，如果您安装 [!DNL Insight Server] 在驱动器C上，将数据集写入驱动器C。

如果您需要 [!DNL Insight Server] 要在其他驱动器上维护数据集，或者如果要收集的数据量需要使用多个驱动器，则必须更新 [!DNL Disk Files.cfg] 文件，指定您想要的位置 [!DNL Insight Server] 写 [!DNL temp.db] 文件。

**配置temp.db的位置**

1. 导航到 [!DNL Components] 文件夹。 [!DNL Insight Server].

   示例：[!DNL C:\Adobe\Server\Components]

1. 打开 [!DNL Disk Files.cfg] 文件（如记事本）。

   默认情况下，此文件在“磁盘文件”结构中包含一个条目，如下所示。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. 更改 [!DNL temp.db]，修改磁盘文件定义。 以下示例说明了如何编辑配置以分散 [!DNL temp.db] 跨驱动器C、D和E的文件：

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
   >请注意，在上述文件名中使用双反斜杠。 在 [!DNL Insight Server] 配置文件中，反斜线字符是转义字符。 它用于在文本中表示特殊的控制序列（例如，\t用于制表符）。 要表示实际的反斜线字符，必须键入反斜线两次（例如，\\）才能覆盖转义函数。 仅当在文本编辑器（如记事本）中编辑配置文件时，这种情况才适用。
