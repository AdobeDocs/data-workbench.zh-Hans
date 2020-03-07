---
description: 在数据工作台中，地形图像层显示地球的地形图像。
solution: Analytics
title: 使用地形图像层
topic: Data workbench
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# 使用地形图像层{#working-with-terrain-image-layers}

在数据工作台中，地形图像层显示地球的地形图像。

Terrain image layers are stored in the [!DNL Geography] profile, in a custom format. 这些图像层可由Adobe生成，或者数据工作台服务器可以将用户提供的地形图像转换为适用于地球可视化的地形层。

>[!NOTE]
>
>To work with terrain image layers, you must install the [!DNL Terrain Images.cfg] file provided by Adobe. 有关安装说明，请参 [阅安装Data Workbench地理位置](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)。

若要定义地形图像层，您必须具有：

* **一个或多个地形图像文件**，其中包含要在地球上显示的图像。
* **一个 Terrain Images.cfg** 文件，指定要用于层的地形图像文件。[!DNL Terrain Images.cfg] 文件允许您添加一个或多个源，以创建地形图像层。地形图像文件的格式决定了应添加的源的类型。下表提供了可用地形图像层源的描述，其中包括受支持的地形图像文件格式：

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 原始的未投影位图 </td> 
   <td colname="col2"> <p>通过经纬度对齐（未投影）的 24 位无标题 RGB 文件创建地形图像层，其中北面是图像的顶部，东面是右部。 </p> <p>支持的图像格式：RAW </p> <p> <p>注意：此源需要投影信息。有关投影格式的信息，请参阅为 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 地形图像指定投影信息</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未投影的一般图像 </td> 
   <td colname="col2"> <p>通过经纬度对齐（未投影）的 24 位图像格式创建地形图像层，其中北面是图像的顶部，东面是右部。 </p> <p>支持的图像格式：BMP、JPG、PNG、TIFF </p> <p> <p>注意：此源需要投影信息。有关投影格式的信息，请参阅为 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 地形图像指定投影信息</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 包含嵌入投影的图像 </td> 
   <td colname="col2"> <p>通过可在图像文件中嵌入大地数据的图像格式创建地形图像层。投影信息提取自该图像。 </p> <p>支持的图像格式：Erdas (IMG)、GeoTIFF </p> <p> <p>注意：此源通常不需要投射信息，但是在需要时支持添加此类信息。有关投影格式的信息，请参阅为 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 地形图像指定投影信息</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**定义地形图像层**

1. 在Data Workbench中，在 [!DNL Admin] >选 [!DNL Dataset and Profile] 项卡上，单击缩 **[!UICONTROL Servers Manager]** 略图以打开工作 [!DNL Servers Manager] 区。

1. Within the [!DNL Servers Manager] window, right-click the icon of the desired data workbench server and click **[!UICONTROL Server Files]**.

1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。

1. Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg.]

1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 The [!DNL Terrain Images.cfg]window appears.

1. 在窗 [!DNL Terrain Images] 口中，单 **[!UICONTROL component]** 击以查看其内容。

1. 右键单击 **[!UICONTROL Sources]** >并 **[!UICONTROL Add new]** 选择以下源类型之一：

   * **[!UICONTROL Raw unprojected bitmap]**。(Once added, this source type is labeled RawTerrainSource in the [!DNL Terrain Images] window.)

   * **[!UICONTROL General image, unprojected]**。(Once added, this source type is labeled GDALTerrainSource in the [!DNL Terrain Images] window.)

   * **[!UICONTROL Image with embedded projection]**。(Once added, this source type is labeled GDALTerrainSource in the [!DNL Terrain Images] window.)

1. 参考以下示例文件和参数表，根据需要编辑源的参数。

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gamma（伽马） </td> 
   <td colname="col2"> 对所有源可选。指定要应用于源图像的 gamma 校正。由于 Data Workbench 通常在高 gamma 设置下运行，因此可能需要该参数。默认值为 1。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Height（高度） </td> 
   <td colname="col2"> 原始未投影位图图像的必选参数。源图像的高度（以像素为单位）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Projection Info（投影信息） </td> 
   <td colname="col2"> <p>原始的未投影位图图像和未投影的一般图像需要该参数，但具有内嵌投影的图像支持该参数。Data workbench<span class="wintitle"> Geography</span> supports latitude-longitude projections and Transverse Mercator (TM) projections for terrain image layers. 默认的投影格式为经纬度投影 (LatLonProjection)。 </p> <p>有关投影格式的信息，请参阅 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 指定地形图像的投影信息</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Source Image（源图像） </td> 
   <td colname="col2">所有源的必选参数。源图像文件的名称。这可能是文件名称或通配符模式。在有些情况下使用模式可能非常有用，例如，上传同一地区、具有不同日期，且相关元数据无更改的图像。Therefore a pattern like “<span class="filepath"> Tysons Corner *.raw</span>” would create layers from <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>, and so on as new images are added, with no additional configuration necessary if the parameters for the files are otherwise identical. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tile Compression Quality（图块压缩质量） </td> 
   <td colname="col2"> <p>对所有源可选。对于 JPEG 压缩，为从 0 到 100 的整数，用来指定如何平衡图像大小和质量。（默认值为零。）较高的数字可产生更好的图像质量，但会生成较大的图像，并会延长 Data Workbench 用户的下载时间。 </p> <p>将图像压缩到70以下可能会导致图像降级。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tile Compressor（图块压缩程序） </td> 
   <td colname="col2"> 对所有源可选。指定用于写入输出文件的压缩方式。当前唯一支持的方式为 RAWRGB（默认设置，其结果是无压缩）和 JPEG。使用 JPEG 压缩可减少在配置文件同步期间传输的层的大小。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Width（宽度） </td> 
   <td colname="col2"> 原始未投影位图图像的必选参数。源图像的宽度（以像素为单位）。 </td> 
  </tr> 
 </tbody> 
</table>

1. 参考下表，编辑 Source Image Location（源图像位置）、Temp Image Storage（临时图像存储）和 Write Layers To（写入层）参数。这些参数适用于该文件 Sources（源）部分中定义的所有地形图像源。

   | 参数 | 描述 |
   |---|---|
   | Source Image Location（源图像位置） | 必需. 进行扫描以查找要转换为地形层的图像的目录。如果它不是绝对路径，可将其解释为相对于 Data Workbench Server 安装目录的路径。 |
   | Temp Image Storage（临时图像存储） | 可选。用于存储将源图像转换为地形层时所用临时文件的目录名称。如果它不是绝对路径，可将其解释为相对于 Data Workbench Server 安装目录的路径。默认位置为 Temp 目录。 |
   | Write Layers To（写入层） | 必需. 输出地形层的目录。 Ordinarily, this is the Maps subdirectory of a profile directory, so that the [!DNL Globe] visualization can find the layers. |

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. 要将更新的文件保存到Data Workbench Server计算机，请在 [!DNL Server Files Manager]列中右键单击对 [!DNL Terrain Images.cfg] 应的复选 [!DNL Temp] 标记，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

