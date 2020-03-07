---
description: Data Workbench 支持所有地形图像层源的经纬度投影和通用横轴墨卡托 (UTM) 投影。
solution: Analytics
title: 指定地形图像的投影信息
topic: Data workbench
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Specify projection information for terrain images{#specify-projection-information-for-terrain-images}

Data Workbench 支持所有地形图像层源的经纬度投影和通用横轴墨卡托 (UTM) 投影。

原始的未投影位图和未投影的一般图像需要投影信息。您可以为包含嵌入投影信息的图像指定投影信息，尽管它通常并不需要此信息，因为投影的参数是由嵌入图像本身的大地数据自动确定的。以下部分提供了有关在 [!DNL Terrain Images.cfg] 文件中指定这些投影格式的详细信息。

## 经纬度投影 {#section-6e335357ec28462ba39c565e0a5986c7}

[!DNL Terrain Images.cfg] 文件中的经纬度投影格式 (LatLonProjection) 由经纬度的四个参数定义。

To specify a LatLonProjection for unprojected images (raw unprojected bitmaps and general images, unprojected), you can enter settings for the LatLonProjection within the [!DNL Terrain Images.cfg] window in Data Workbench.

若要为包含嵌入投影信息的图像指定 ，必须在文本编辑器（如记事本）中打开 [!DNL Terrain Images.cfg] 文件，将 Projection Info（投影信息）参数设置为 LatLonProjection，然后添加 [!DNL LatLonProjection]LatLonProjection 的设置。

**为未投影的图像指定 LatLonProjection**

1. 在Data Workbench [!DNL Terrain Images.cfg] 中打开文件，并添加地形图像层源，如 [To define a terrain image layer中所述](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)。
1. 参考以下参数表，编辑 Projection Info（投影信息）参数：

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>图像顶部边缘的纬度（以度为单位），其中 90 表示北极，-90 表示南极。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>图像底部边缘的纬度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>图像左侧边缘的经度（以度为单位），其中正数表示东经，负数表示西经。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>图像右侧边缘的经度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.
1. 要将本地所做的更改保存到Data Workbench Server计算机，请在 [!DNL Server Files Manager]列中右键单击对应的复选标记，然后单击 [!DNL Terrain Images.cfg] > [!DNL Temp] &lt; **[!UICONTROL Save to]** > ***[!UICONTROL server name]***。

**为包含嵌入投影信息的图像指定 LatLonProjection**

在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。

Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg].

右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 文件 [!DNL Terrain Images.cfg] 显示在记事本窗口中。

参考以下示例文件片段，编辑 Projection Info（投影信息）参数。请务必将投影类型指定为以下突出显示的内容。有关这些参数的描述，请参阅上一步骤中的“LatLonProjection 参数”表。

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## 通用横轴墨卡托投影 {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

通用横轴墨卡托 (UTM) 投影由八个参数定义。在为地形图像层指定通用横轴墨卡托投影时，您的地形图像文件必须与朝向图像顶部的北伪偏移（已投影）对齐，并与朝向图像右侧的东伪偏移对齐。

若要为任何地形图像源指定 UTM 投影，必须在文本编辑器（如记事本）中打开 [!DNL Terrain Images.cfg] 文件，将 Projection Info（投影信息）参数设置为“TransverseMercatorProjection”，然后添加 UTM 投影的设置。

**指定通用横轴墨卡托投影**

1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。
1. Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg.]
1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 文件 [!DNL Terrain Images.cfg] 显示在记事本窗口中。
1. 参考以下示例文件片段和参数表，编辑 Projection Info（投影信息）参数。请务必将投影类型指定为以下突出显示的内容。

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ellipsoid Inverse Flattening（椭球体逆向平展）、Ellipsoid Semimajor Axis（椭球体半长轴） </p> </td> 
   <td colname="col2"> <p>用于投影的椭球体参数。椭球体的半长轴以米为单位指定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Easting（东伪偏移） </p> </td> 
   <td colname="col2"> <p>投影的中央子午线的东伪偏移（以米为单位）。对于 UTM，该值始终为 500,000。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Northing（北伪偏移） </p> </td> 
   <td colname="col2"> <p>投影中赤道的北伪偏移（以米为单位）。对于 UTM，0 表示北半球区域，10,000 表示南半球区域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Northwest Corner Coordinates（西北角坐标）、Southeast Corner Coordinates（东南角坐标） </p> </td> 
   <td colname="col2"> <p>图像左上角和右下角的坐标（以投影的米为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridian（本初子午线） </p> </td> 
   <td colname="col2"> <p>投影的中央子午线的经度，以格林威治的东经度数指定。负数可用来指定西经度数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scale Factor（缩放因子） </p> </td> 
   <td colname="col2"> <p>投影柱体半径与椭球体半长轴的比率。对于通用横轴墨卡托 (UTM) 投影，该值始终为 0.9996。 </p> </td> 
  </tr> 
 </tbody> 
</table>

