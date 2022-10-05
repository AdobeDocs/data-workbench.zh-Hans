---
description: 有关元素点层列的信息。
title: 元素点查找文件格式
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 34%

---

# 元素点查找文件格式{#element-point-lookup-file-format}

{{eol}}

有关元素点层列的信息。

元素点层查找文件必须至少包含以下三列：

* **[!DNL Key]列：** 此列应包含通用键数据，这允许Data Workbench Server将查找文件中的数据与数据集中的数据进行连接。 的 [!DNL Key] 列必须是查找文件中的第一列。 此列中的每一行都标识维度中的一个元素。

* **[!DNL Longitude]列：** 此列应包含中每个数据点的经度 [!DNL Key] 列。

* **[!DNL Latitude]列：** 此列应包含 [!DNL Key] 列。

* **[!DNL Name]列：** （可选）。 如果要为每个数据点指定要在映射中显示的名称，您可以包括 [!DNL Name] 列。

[!DNL Zip Points.txt] 查找文件中的每一行在第一列中包含邮政编码，随后是经度、纬度和关联的城市名称。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
