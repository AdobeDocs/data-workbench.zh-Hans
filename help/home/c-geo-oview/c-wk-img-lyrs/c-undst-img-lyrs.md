---
description: 有关地理位置配置文件层、图像层类型和创建新层的概念性信息。
solution: Analytics
title: 了解图像层
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解图像层{#understanding-imagery-layers}

有关地理位置配置文件层、图像层类型和创建新层的概念性信息。

## 图像层的类型 {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench使 [!DNL Geography] 您能够在Data Workbench中查看以下类型的图像层：

* **地形图像层：** 这种层显示地球的地形图像，可在其上显示地理数据。 数据工作台中的地球可视化是一个地形图像层的示例。 See [Working with Terrain Image Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **元素点层：** 此类型的图层在地球仪上显示一个尺寸的每个元素的一个点。 See [Working with Element Point Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **矢量层：** 此类层在地球仪上显示矢量数据（线状图）。 See [Working with Vector Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

在 Data Workbench 中，您可以从这些层中选择需要为特定分析任务显示的层。

## 地域配置文件层 {#section-4d9fb9b357764493a4d97d2b4068bb67}

“[!DNL Geography]地域”配置文件为您提供了一组默认的图像层，它们存储在 Data Workbench Server 安装目录的 Profiles\Maps 文件夹中：

* **蓝色大理石2公里：** 此地形图像层创建世界的3D地图，当您将地球可视化添加到工作区时，将显示该地图。 在该层未被选中时，将看不到地球，但其他层仍会显示。文 [!DNL Blue Marble 2km.layer] 件引用该 [!DNL Blue Marble 2km.tsi] 文件。

   有关使用全局可视化的信息，请参阅《 *Data Workbench用户指南》*。

* **Zip点：** 此元素点层允许您使用美国邮政编码映射数据集中的位置。 [!DNL Zip Points.txt] 查找文件（由 Adobe 提供）包含所有美国邮政编码以及每个邮政编码经纬度的列表。The [!DNL Zip Points.layer] file references the [!DNL Zip Points.txt] file and the [!DNL Zipcode.dim] file and contains the configuration parameters needed to display the locations on the globe. 在数据集内定义的每个“邮政编码”维度 ([!DNL Zipcode.dim]) 元素都是使用 [!DNL Zip Points.txt] 查找文件中针对该邮政编码列出的经纬度映射到地球上的。

   For information about defining dimensions, see the *Dataset Configuration Guide.*

* **边界：** 该矢量层提供了世界主要政治边界（如国家）以及地球的自然物理特征边界（如湖泊和岛屿）。 文 [!DNL Boundaries.layer] 件引用一个或多个、、、、 [!DNL mwcoast.vec]、 [!DNL mwisland.vec]、和 [!DNL mwlake.vec][!DNL mwnation.vec][!DNL mwriver.vec][!DNL mwstate.vec][!DNL US states.vec][!DNL world boundaries.vec] 文件。

* **IP坐标：** 此元素点层使用动态点使您能够使用IP地址映射数据集中的位置。 [!DNL IP Coordinates.layer] 文件引用了“坐标”维度 ([!DNL Coordinates.dim])，并指定“访客数”量度作为确定地球上每个坐标点大小的量度。

Your [!DNL Geography] profile or other profiles in your installation may contain additional imagery layers that Adobe provided or your company created.

## 创建新层 {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

You can create new imagery layers by copying the appropriate type of layer file included in the [!DNL Geography] profile into any Profiles\*profile name*\Maps folder, then renaming and editing the file as appropriate. 所有新层必须满足以下要求：

* The [!DNL .layer] file must adhere to the format of one of the supported layer types.
* The [!DNL .layer] file must reference the appropriate lookup and dimension files, if necessary.
* The referenced lookup file also must be stored within the data workbench server installation directory, and its path must be specified accurately in the [!DNL .layer] file.

有关每种类型层文件及其相关文件的格式和参数的详细信息，请参阅本章中相应的层类型所对应的部分。
