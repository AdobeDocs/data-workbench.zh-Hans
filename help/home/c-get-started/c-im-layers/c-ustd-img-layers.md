---
description: 有关图像层的概念性信息。
solution: Analytics
title: 关于图像图层
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: f4b37f50b115a1e1d2c9d000897a8fa47b03b233
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 60%

---


# 关于图像图层{#about-imagery-layers}

有关图像层的概念性信息。

## Types of imagery layers {#section-891cbf61e8334690bd203a2bb9761b25}

您可以在Data Workbench中视图以下类型的图像层：

* **[!UICONTROL 地形图像层]：**&#x200B;此类层显示地球的地形图像，在该图像上可显示地理数据。地球可视化是地形图像层的一个示例。请参阅 [使用地形图像图层](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL 元素点层]：**&#x200B;此类层在地球上针对维度的每个元素显示一个点。See [Working with Element Point Layers](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL 矢量层]：**&#x200B;此类层在地球上显示矢量数据（艺术线条）。See [Working with Vector Layers](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL 表示层]** -使用表示层叠加注释和阐明可视化。 增添了文本标注、箭头、图像和颜色编码，以便突出显示和阐明您的数据，随后可与他人共享这些数据。

在Data Workbench中，您可以选择要为特定分析任务显示的这些图层中的哪个。

## Geography profile layers {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

The [!DNL Geography] profile provides you with a set of default imagery layers, which are stored in the Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL 蓝色大理石 2km]：**&#x200B;此地形图像层创建一个三维世界地图，在向工作区中添加地球可视化时将显示该层。在该层未被选中时，将看不到地球，但其他层仍会显示。文 [!DNL Blue Marble 2km.layer] 件引用该 [!DNL Blue Marble 2km.tsi] 文件。

* **[!UICONTROL 邮政编码点]：**&#x200B;此元素点层让您能够使用美国邮政编码映射数据集中的位置。[!DNL Zip Points.txt] 查找文件（由 Adobe 提供）包含所有美国邮政编码以及每个邮政编码经纬度的列表。The [!DNL Zip Points.layer] file references the [!DNL Zip Points.txt] file and the [!DNL Zipcode.dim] file and contains the configuration parameters needed to display the locations on the globe. 在数据集内定义的每个“邮政编码”维度 ([!DNL Zipcode.dim]) 元素都是使用 [!DNL Zip Points.txt] 查找文件中针对该邮政编码列出的经纬度映射到地球上的。

   有关定义维度的信息，请参阅《数据集配置指南》**。

* **[!UICONTROL 边界]：**&#x200B;此矢量层提供了主要的世界政治边界（例如国家/地区）以及地球上自然物理特征的边界（例如湖泊和岛屿）。文 [!DNL Boundaries.layer] 件引用一个或多个 [!DNL mwcoast.vec]、、、 [!DNL mwisland.vec]、 [!DNL mwlake.vec]、 [!DNL mwnation.vec]、 [!DNL mwriver.vec]和 [!DNL mwstate.vec][!DNL US states.vec][!DNL world boundaries.vec] 文件。

* **[!UICONTROL IP 坐标]：**&#x200B;此元素点层使用动态点让您能够使用 IP 地址映射数据集中的位置。[!DNL IP Coordinates.layer] 文件引用了“坐标”维度 ([!DNL Coordinates.dim])，并指定“访客数”量度作为确定地球上每个坐标点大小的量度。

Your [!UICONTROL NL Geography] profile or other profiles in your installation may contain additional imagery layers that Adobe provided or your company created.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

You can create new imagery layers by copying the appropriate type of layer file included in the [!DNL Geography] profile into any Profiles\*profile name*\Maps folder, then renaming and editing the file as appropriate. 所有新层必须满足以下要求：

* The [!DNL .layer] file must adhere to the format of one of the supported layer types.
* The [!DNL .layer] file must reference the appropriate lookup and dimension files, if necessary.
* The referenced lookup file also must be stored within the Data Workbench server installation directory, and its path must be specified accurately in the [!DNL .layer] file.

有关每种类型层文件及其相关文件的格式和参数的详细信息，请参阅本章中相应的层类型所对应的部分。
