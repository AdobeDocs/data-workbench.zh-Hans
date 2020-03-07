---
description: Terrain Images.cfg 文件中的经纬度投影格式 (LatLonProjection) 由经纬度的四个参数定义。
solution: Analytics
title: 经纬度投影
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 经纬度投影{#latitude-longitude-projections}

Terrain Images.cfg 文件中的经纬度投影格式 (LatLonProjection) 由经纬度的四个参数定义。

若要为未投影图像（原始的未投影位图和未投影的一般图像）指定 LatLonProjection，可以在 Data Workbench 中的 [!DNL Terrain Images.cfg] 窗口内输入 LatLonProjection 的设置。See [To specify a LatLonProjection for unprojected images](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

To specify a LatLonProjection for images with embedded projection information, you must open the [!DNL Terrain Images.cfg] file in a text editor such as Notepad, set the Projection Info parameter to “LatLonProjection”, and add settings for the LatLonProjection. See [To specify a LatLonProjection for images within embedded projection information...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [为未投影的图像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [要为嵌入的投影信息中的图像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## To Specify a LatLonProjection for Unprojected Images {#section-26554eefe645481faba68396fa13756a}

1. 在Data Workbench [!DNL Terrain Images.cfg] 中打开文件，并添加地形图像层源，如 [To define a terrain image layer](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)。

1. 参考以下参数表，编辑 Projection Info（投影信息）参数：

   | 参数 | 描述 |
   |---|---|
   | Lat0 | 图像顶部边缘的纬度（以度为单位），其中 90 表示北极，-90 表示南极。 |
   | Lat1 | 图像底部边缘的纬度。 |
   | Lon0 | 图像左侧边缘的经度（以度为单位），其中正数表示东经，负数表示西经。 |
   | Lon1 | 图像右侧边缘的经度。 |

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. 要将本地所做的更改保存到Data Workbench Server计算机，请在 [!DNL Server Files Manager]列中右键单击对应的复选标记，然 [!DNL Terrain Images.cfg] 后单 [!DNL Temp] 击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## To Specify a LatLonProjection for Images Within Embedded Projection Information {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。

1. Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg].

1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 文件 [!DNL Terrain Images.cfg] 显示在记事本窗口中。

1. 参考以下示例文件片段，编辑 Projection Info（投影信息）参数。请务必将投影类型指定为以下突出显示的内容。有关这些参数的描述，请参阅上一步骤中的“LatLonProjection 参数”表。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

