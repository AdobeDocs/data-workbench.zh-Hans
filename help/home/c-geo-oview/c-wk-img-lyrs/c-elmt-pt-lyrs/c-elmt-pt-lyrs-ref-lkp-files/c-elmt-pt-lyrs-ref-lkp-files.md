---
description: 在创建引用查找文件以获取经纬度数据的元素点层时，可通过在查找文件中检索每个元素及其关联的经纬度来获取点的位置。
solution: Analytics
title: 定义引用查找文件的元素点层
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定义引用查找文件的元素点层{#defining-element-point-layers-referencing-lookup-files}

在创建引用查找文件以获取经纬度数据的元素点层时，可通过在查找文件中检索每个元素及其关联的经纬度来获取点的位置。

Instead of using a lookup file, you can use the [!DNL Dynamic Points] functionality, which embeds the latitude and longitude of a location in the name of each element of a dimension. See [Defining Element Point Layers Using Dynamic Points](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

若要定义引用查找文件的元素点层，必须创建或已经具有以下信息：

* **维度**，在 [!DNL Transformation.cfg] 文件或转换数据集包含文件中定义。有关转换配置文件的信息，请参阅《数据集配置指南》**。

* **查找文件**，包含用于绘制每个数据点的数据。此文件必须针对每个数据点至少包含三个数据列：键、经度和纬度。For more information about the required format of the lookup file, see [Element Point Lookup File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **层文件**，指定查找文件的位置并标识相关的维度和量度以及查找文件中的键、经度和纬度列名称。有关层文件所需格式的详细信息，请参阅[元素点层文件格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)。

>[!NOTE]
>
>The [!DNL Zip Points.layer] file, provided with the [!DNL Geography] profile, is an element point layer that identifies the [!DNL Zipcode.dim] file, the [!DNL Sessions.metric] file, the [!DNL Zip Points.txt] lookup file, and the names of the key, longitude, latitude, and name columns in the lookup file.

