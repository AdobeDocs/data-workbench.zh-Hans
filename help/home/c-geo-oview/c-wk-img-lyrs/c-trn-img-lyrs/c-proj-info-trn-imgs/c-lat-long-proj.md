---
description: Terrain Images.cfg 文件中的经纬度投影格式 (LatLonProjection) 由经纬度的四个参数定义。
title: 经纬投影
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 50%

---

# 经纬投影{#latitude-longitude-projections}

{{eol}}

Terrain Images.cfg 文件中的经纬度投影格式 (LatLonProjection) 由经纬度的四个参数定义。

若要为未投影图像（原始的未投影位图和未投影的一般图像）指定 LatLonProjection，可以在 Data Workbench 中的 [!DNL Terrain Images.cfg] 窗口内输入 LatLonProjection 的设置。请参阅 [为未投影图像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

要为具有嵌入投影信息的图像指定LatLonProjection，必须打开 [!DNL Terrain Images.cfg] 在文本编辑器（如记事本）中，将Projection Info（投影信息）参数设置为“LatLonProjection”，并添加LatLonProjection的设置。 请参阅 [要为嵌入投影信息中的图像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [为未投影图像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [要为嵌入投影信息中的图像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 为未投影图像指定LatLonProjection {#section-26554eefe645481faba68396fa13756a}

1. 打开 [!DNL Terrain Images.cfg] 文件，并按 [定义地形图像图层](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. 参考以下参数表，编辑 Projection Info（投影信息）参数：

   | 参数 | 描述 |
   |---|---|
   | Lat0 | 图像顶部边缘的纬度（以度为单位），其中 90 表示北极，-90 表示南极。 |
   | Lat1 | 图像底部边缘的纬度。 |
   | Lon0 | 图像左侧边缘的经度（以度为单位），其中正数表示东经，负数表示西经。 |
   | Lon1 | 图像右侧边缘的经度。 |

1. 通过右键单击保存文件 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

1. 要将本地所做的更改保存到Data Workbench Server计算机，请在 [!DNL Server Files Manager]，右键单击的复选标记 [!DNL Terrain Images.cfg] 在 [!DNL Temp] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 为嵌入投影信息中的图像指定LatLonProjection {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Components]** 查看其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。

1. 右键单击“服务器名称”列中的复选标记 [!DNL Terrain Images.cfg]，然后单击 **[!UICONTROL Make Local]**. 在 [!DNL Temp] 列 [!DNL Terrain Images.cfg].

1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 的 [!DNL Terrain Images.cfg] 文件会在记事本窗口中显示。

1. 参考以下示例文件片段，编辑 Projection Info（投影信息）参数。请务必将投影类型指定为以下突出显示的内容。有关这些参数的描述，请参阅上一步骤中的“LatLonProjection 参数”表。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
