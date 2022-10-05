---
description: 有关地理配置文件层、图像层类型和创建新层的概念信息。
title: 了解图像图层
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 33%

---

# 了解图像图层{#understanding-imagery-layers}

{{eol}}

有关地理配置文件层、图像层类型和创建新层的概念信息。

## 图像层的类型 {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] 允许您在Data Workbench中查看以下类型的图像层：

* **地形图像层：** 此类型的层显示地球的地形图像，可在其上显示地理数据。 Data Workbench中的地球可视化是地形图像层的一个示例。 请参阅 [使用地形图像图层](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **元素点层：** 此类型的层在地球上针对维度的每个元素显示一个点。 请参阅 [使用元素点层](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **矢量层：** 此类层在地球上显示矢量数据（线条图）。 请参阅 [使用矢量层](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

在 Data Workbench 中，您可以从这些层中选择需要为特定分析任务显示的层。

## 地域配置文件层 {#section-4d9fb9b357764493a4d97d2b4068bb67}

“[!DNL Geography]地域”配置文件为您提供了一组默认的图像层，它们存储在 Data Workbench Server 安装目录的 Profiles\Maps 文件夹中：

* **蓝色大理石2公里：** 此地形图像层可创建世界的3D地图，当您将地球可视化添加到工作区时，将显示该地图。 在该层未被选中时，将看不到地球，但其他层仍会显示。的 [!DNL Blue Marble 2km.layer] 文件引用 [!DNL Blue Marble 2km.tsi] 文件。

   有关使用地球可视化的信息，请参阅 *Data Workbench用户指南*.

* **邮政点：** 此元素点层允许您使用美国邮政编码映射数据集中的位置。 [!DNL Zip Points.txt] 查找文件（由 Adobe 提供）包含所有美国邮政编码以及每个邮政编码经纬度的列表。的 [!DNL Zip Points.layer] 文件引用 [!DNL Zip Points.txt] 文件和 [!DNL Zipcode.dim] 文件，并包含显示地球上的位置所需的配置参数。 在数据集内定义的每个“邮政编码”维度 ([!DNL Zipcode.dim]) 元素都是使用 [!DNL Zip Points.txt] 查找文件中针对该邮政编码列出的经纬度映射到地球上的。

   有关定义维度的信息，请参阅 *数据集配置指南。*

* **边界：** 这一矢量层提供了世界主要政治边界，如国家，以及地球的自然物理特征边界，如湖泊和岛屿。 的 [!DNL Boundaries.layer] 文件引用一个或多个 [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]和 [!DNL world boundaries.vec] 文件。

* **IP坐标：** 此元素点层使用动态点让您能够使用IP地址映射数据集中的位置。 [!DNL IP Coordinates.layer] 文件引用了“坐标”维度 ([!DNL Coordinates.dim])，并指定“访客数”量度作为确定地球上每个坐标点大小的量度。

您的 [!DNL Geography] 配置文件或安装中的其他配置文件可能包含Adobe提供或您的公司创建的其他图像层。

## 创建新层 {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

您可以通过复制 [!DNL Geography] 将配置文件移入任意Profiles\*配置文件名称*\Maps文件夹，然后根据需要重命名和编辑文件。 所有新层必须满足以下要求：

* 的 [!DNL .layer] 文件必须遵循其中一种受支持层类型的格式。
* 的 [!DNL .layer] 文件必须引用相应的查找和维度文件（如果需要）。
* 引用的查找文件还必须存储在Data Workbench Server安装目录中，并且其路径必须在 [!DNL .layer] 文件。

有关每种类型层文件及其相关文件的格式和参数的详细信息，请参阅本章中相应的层类型所对应的部分。
