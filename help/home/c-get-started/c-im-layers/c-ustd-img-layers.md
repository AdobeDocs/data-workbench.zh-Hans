---
description: 有关图像层的概念性信息。
title: 关于图像图层
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 36%

---

# 关于图像图层{#about-imagery-layers}

有关图像层的概念性信息。

## 影像层类型{#section-891cbf61e8334690bd203a2bb9761b25}

您可以在Data Workbench中视图以下类型的图像层：

* **[!UICONTROL Terrain image layer]:** 此类层显示地球的地形图像，可在其上显示地理数据。地球可视化是地形图像层的一个示例。请参阅 [使用地形图像图层](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** 此类型的图层在地球上显示尺寸的每个元素的一个点。请参阅[使用元素点层](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd)。

* **[!UICONTROL Vector layer]:** 此类图层在地球上显示矢量数据（线图）。请参阅[使用矢量图层](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9)。

* **[!UICONTROL Presentation layer]**&#x200B;使用演示叠加图来标注和阐明可视化。增添了文本标注、箭头、图像和颜色编码，以便突出显示和阐明您的数据，随后可与他人共享这些数据。

在Data Workbench中，您可以选择要针对特定分析任务显示的这些图层中的哪个。

## 地理用户档案层{#section-d04ab9f1a8cd4c6580e48ce44ac51898}

[!DNL Geography]用户档案为您提供了一组默认图像层，这些图像层存储在Profiles\Geography\Maps folder within the Data Workbench server installation directory文件夹中：

* **[!UICONTROL Blue Marble 2km]:** 此地形图像层创建世界的3-D地图，当您将地球可视化添加到工作区时将显示该地图。在该层未被选中时，将看不到地球，但其他层仍会显示。[!DNL Blue Marble 2km.layer]文件引用[!DNL Blue Marble 2km.tsi]文件。

* **[!UICONTROL Zip Points]:** 此元素点层使您能够使用美国邮政编码映射数据集中的位置。[!DNL Zip Points.txt] 查找文件（由 Adobe 提供）包含所有美国邮政编码以及每个邮政编码经纬度的列表。[!DNL Zip Points.layer]文件引用[!DNL Zip Points.txt]文件和[!DNL Zipcode.dim]文件，并包含显示地球仪上的位置所需的配置参数。 在数据集内定义的每个“邮政编码”维度 ([!DNL Zipcode.dim]) 元素都是使用 [!DNL Zip Points.txt] 查找文件中针对该邮政编码列出的经纬度映射到地球上的。

   有关定义维度的信息，请参阅《数据集配置指南》**。

* **[!UICONTROL Boundaries]:** 这一矢量层提供了世界主要政治边界，如国家，以及地球的自然物理特征边界，如湖泊和岛屿。[!DNL Boundaries.layer]文件引用[!DNL mwcoast.vec]、[!DNL mwisland.vec]、[!DNL mwlake.vec]、[!DNL mwnation.vec]、[!DNL mwriver.vec]、[!DNL mwstate.vec]、[!DNL US states.vec]和[!DNL world boundaries.vec]文件中的一个或多个。

* **[!UICONTROL IP Coordinates]:** 此元素点层使用动态点，使您能够使用IP地址映射数据集中的位置。[!DNL IP Coordinates.layer] 文件引用了“坐标”维度 ([!DNL Coordinates.dim])，并指定“访客数”量度作为确定地球上每个坐标点大小的量度。

您的[!UICONTROL NL Geography]用户档案或安装中的其他用户档案可能包含Adobe提供的其他图像层或您创建的公司。

## 创建新图层{#section-b5313773316c4e0fa748f7376a8e7f0b}

您可以创建新的影像图层，方法是将[!DNL Geography]用户档案中包含的适当类型的图层文件复制到任何用户档案\*用户档案名称*\Maps文件夹中，然后根据需要重命名和编辑文件。 所有新层必须满足以下要求：

* [!DNL .layer]文件必须遵循其中一种受支持的图层类型的格式。
* 如果需要，[!DNL .layer]文件必须引用相应的查找和维文件。
* 引用的查找文件也必须存储在Data Workbench服务器安装目录中，并且必须在[!DNL .layer]文件中准确指定其路径。

有关每种类型层文件及其相关文件的格式和参数的详细信息，请参阅本章中相应的层类型所对应的部分。
