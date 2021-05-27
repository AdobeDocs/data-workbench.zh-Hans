---
description: 在Data Workbench中，地形图像层显示地球的地形图像。
title: 使用地形图像图层
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 64%

---

# 使用地形图像图层{#working-with-terrain-image-layers}

在Data Workbench中，地形图像层显示地球的地形图像。

地形图像层以自定义格式存储在[!DNL Geography]配置文件中。 这些图像层可以由Adobe生成，或者Data Workbench Server可以将用户提供的地形图像转换为适用于地球可视化的地形层。

>[!NOTE]
>
>要使用地形图像层，必须安装由Adobe提供的[!DNL Terrain Images.cfg]文件。 有关安装说明，请参阅[安装Data Workbench地理位置](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)。

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
   <td colname="col2"> <p>通过经纬度对齐（未投影）的 24 位无标题 RGB 文件创建地形图像层，其中北面是图像的顶部，东面是右部。 </p> <p>支持的图像格式：RAW </p> <p> <p>注意：此源需要投影信息。有关投影格式的信息，请参阅<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">为地形图像指定投影信息</a> 。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未投影的一般图像 </td> 
   <td colname="col2"> <p>通过经纬度对齐（未投影）的 24 位图像格式创建地形图像层，其中北面是图像的顶部，东面是右部。 </p> <p>支持的图像格式：BMP、JPG、PNG、TIFF </p> <p> <p>注意：此源需要投影信息。有关投影格式的信息，请参阅<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">为地形图像指定投影信息</a> 。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 包含嵌入投影的图像 </td> 
   <td colname="col2"> <p>通过可在图像文件中嵌入大地数据的图像格式创建地形图像层。投影信息提取自该图像。 </p> <p>支持的图像格式：Erdas (IMG)、GeoTIFF </p> <p> <p>注意：此源通常不需要投射信息，但是在需要时支持添加此类信息。有关投影格式的信息，请参阅<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">为地形图像指定投影信息</a> 。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**定义地形图像层**

1. 在Data Workbench的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开[!DNL Servers Manager]工作区。

1. 在[!DNL Servers Manager]窗口中，右键单击所需Data Workbench Server的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;以查看其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。

1. 右键单击服务器名称列中[!DNL Terrain Images.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中出现[!DNL Terrain Images.cfg.]的复选标记

1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现[!DNL Terrain Images.cfg]窗口。

1. 在[!DNL Terrain Images]窗口中，单击&#x200B;**[!UICONTROL component]**&#x200B;以查看其内容。

1. 右键单击&#x200B;**[!UICONTROL Sources]** > **[!UICONTROL Add new]**&#x200B;并选择以下源类型之一：

   * **[!UICONTROL Raw unprojected bitmap]**。（添加后，此源类型将在[!DNL Terrain Images]窗口中标记为RawTerrainSource。）

   * **[!UICONTROL General image, unprojected]**。（添加后，此源类型将在[!DNL Terrain Images]窗口中标记为GDALTerrainSource。）

   * **[!UICONTROL Image with embedded projection]**。（添加后，此源类型将在[!DNL Terrain Images]窗口中标记为GDALTerrainSource。）

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
   <td colname="col2"> <p>原始的未投影位图图像和未投影的一般图像需要该参数，但具有内嵌投影的图像支持该参数。Data Workbench<span class="wintitle"> Geography</span>支持地形图像层的经纬度投影和横轴墨卡托(TM)投影。 默认的投影格式为经纬度投影 (LatLonProjection)。 </p> <p>有关投影格式的信息，请参阅 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 指定地形图像的投影信息</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Source Image（源图像） </td> 
   <td colname="col2">所有源的必选参数。源图像文件的名称。这可能是文件名称或通配符模式。在有些情况下使用模式可能非常有用，例如，上传同一地区、具有不同日期，且相关元数据无更改的图像。因此，像“<span class="filepath"> Tysons Corner *.raw</span>”这样的模式会在添加新图像时从<span class="filepath"> Tysons Corner 050211.raw</span>、<span class="filepath"> Tysons Corner 050218.raw</span>等创建层，如果文件的参数不同，则无需进行其他配置。 </td> 
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
   | Source Image Location（源图像位置） | 必需。进行扫描以查找要转换为地形层的图像的目录。如果它不是绝对路径，可将其解释为相对于 Data Workbench Server 安装目录的路径。 |
   | Temp Image Storage（临时图像存储） | 可选。用于存储将源图像转换为地形层时所用临时文件的目录名称。如果它不是绝对路径，可将其解释为相对于 Data Workbench Server 安装目录的路径。默认位置为 Temp 目录。 |
   | Write Layers To（写入层） | 必需。地形层输出到的目录。 通常，这是配置文件目录的Maps子目录，以便[!DNL Globe]可视化图表可以找到层。 |

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**&#x200B;并单击&#x200B;**[!UICONTROL Save]**&#x200B;保存文件。

1. 要将更新的文件保存到Data Workbench Server计算机，请在[!DNL Server Files Manager]列中右键单击[!DNL Terrain Images.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。[!DNL Temp]
