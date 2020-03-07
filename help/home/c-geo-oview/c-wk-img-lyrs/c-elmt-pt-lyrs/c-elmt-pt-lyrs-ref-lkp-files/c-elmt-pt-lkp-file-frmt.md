---
description: 有关元素点层列的信息。
solution: Analytics
title: 元素点查找文件格式
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 元素点查找文件格式{#element-point-lookup-file-format}

有关元素点层列的信息。

元素点层查找文件必须至少包含以下三列：

* **[!DNL Key]列：**此列应包含常用键数据，这使Data Workbench Server能够将查找文件中的数据连接到数据集中的数据。 The[!DNL Key]column must be the first column in the lookup file. 此列中的每一行都标识维度中的一个元素。

* **[!DNL Longitude]列：**此列应包含列中每个数据点的经[!DNL Key]度。

* **[!DNL Latitude]列：**此列应包含列中每个数据点的纬度[!DNL Key]值。

* **[!DNL Name]列：**（可选）。 If you want to specify a name to be displayed on the map for each data point, you can include a[!DNL Name]column in the lookup file.

[!DNL Zip Points.txt] 查找文件中的每一行在第一列中包含邮政编码，随后是经度、纬度和关联的城市名称。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

