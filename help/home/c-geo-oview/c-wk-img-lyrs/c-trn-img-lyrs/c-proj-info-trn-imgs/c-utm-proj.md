---
description: 通用横轴墨卡托 (UTM) 投影由八个参数定义。
title: 通用横轴墨卡托投影
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 86%

---

# 通用横轴墨卡托投影{#universal-transverse-mercator-projections}

{{eol}}

通用横轴墨卡托 (UTM) 投影由八个参数定义。

在为地形图像层指定通用横轴墨卡托投影时，您的地形图像文件必须与朝向图像顶部的北伪偏移（已投影）对齐，并与朝向图像右侧的东伪偏移对齐。

若要为任何地形图像源指定 UTM 投影，必须在文本编辑器（如记事本）中打开 [!DNL Terrain Images.cfg] 文件，将 Projection Info（投影信息）参数设置为“TransverseMercatorProjection”，然后添加 UTM 投影的设置。

**指定通用横轴墨卡托投影**

1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Components]** 查看其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。

1. 右键单击 *服务器名称* 列 [!DNL Terrain Images.cfg]，然后单击 **[!UICONTROL Make Local]**. 在 [!DNL Temp] 列 [!DNL Terrain Images.cfg].

1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 的 [!DNL Terrain Images.cfg]文件会在记事本窗口中显示。

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

| 参数 | 描述 |
|---|---|
| Ellipsoid Inverse Flattening（椭球体逆向平展）、Ellipsoid Semimajor Axis（椭球体半长轴） | 用于投影的椭球体参数。椭球体的半长轴以米为单位指定。 |
| False Easting（东伪偏移） | 投影的中央子午线的东伪偏移（以米为单位）。对于 UTM，该值始终为 500,000。 |
| False Northing（北伪偏移） | 投影中赤道的北伪偏移（以米为单位）。对于 UTM，0 表示北半球区域，10,000 表示南半球区域。 |
| Northwest Corner Coordinates（西北角坐标）、Southeast Corner Coordinates（东南角坐标） | 图像左上角和右下角的坐标（以投影的米为单位）。 |
| Prime Meridian（本初子午线） | 投影的中央子午线的经度，以格林威治的东经度数指定。负数可用来指定西经度数。 |
| Scale Factor（缩放因子） | 投影柱体半径与椭球体半长轴的比率。对于通用横轴墨卡托 (UTM) 投影，该值始终为 0.9996。 |
