---
description: 在创建引用查找文件以获取经纬度数据的元素点层时，可通过在查找文件中检索每个元素及其关联的经纬度来获取点的位置。
title: 定义引用查找文件的元素点层
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 70%

---

# 定义引用查找文件的元素点层{#defining-element-point-layers-referencing-lookup-files}

在创建引用查找文件以获取经纬度数据的元素点层时，可通过在查找文件中检索每个元素及其关联的经纬度来获取点的位置。

您可以使用[!DNL Dynamic Points]功能而不是使用查找文件，该功能将位置的纬度和经度嵌入维度每个元素的名称中。 请参阅[使用动态点定义元素点层](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

若要定义引用查找文件的元素点层，必须创建或已经具有以下信息：

* **维度**，在 [!DNL Transformation.cfg] 文件或转换数据集包含文件中定义。有关转换配置文件的信息，请参阅《数据集配置指南》**。

* **查找文件**，包含用于绘制每个数据点的数据。此文件必须针对每个数据点至少包含三个数据列：键、经度和纬度。有关查找文件所需格式的更多信息，请参阅[元素点查找文件格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121)。

* **层文件**，指定查找文件的位置并标识相关的维度和量度以及查找文件中的键、经度和纬度列名称。有关层文件所需格式的详细信息，请参阅[元素点层文件格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)。

>[!NOTE]
>
>随[!DNL Geography]配置文件提供的[!DNL Zip Points.layer]文件是一个元素点层，用于标识[!DNL Zipcode.dim]文件、[!DNL Sessions.metric]文件、[!DNL Zip Points.txt]查找文件以及查找文件中键、经度、纬度和名称列的名称。
