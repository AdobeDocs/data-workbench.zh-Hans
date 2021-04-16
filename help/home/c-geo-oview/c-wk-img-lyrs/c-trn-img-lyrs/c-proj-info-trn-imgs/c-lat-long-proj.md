---
description: Terrain Images.cfg 文件中的经纬度投影格式 (LatLonProjection) 由经纬度的四个参数定义。
title: 经纬度投影
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 50%

---

# 经纬度投影{#latitude-longitude-projections}

Terrain Images.cfg 文件中的经纬度投影格式 (LatLonProjection) 由经纬度的四个参数定义。

若要为未投影图像（原始的未投影位图和未投影的一般图像）指定 LatLonProjection，可以在 Data Workbench 中的 [!DNL Terrain Images.cfg] 窗口内输入 LatLonProjection 的设置。请参阅[为未投影图像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)。

要为具有嵌入投影信息的图像指定LatLonProjection，必须在文本编辑器（如记事本）中打开[!DNL Terrain Images.cfg]文件，将“投影信息”参数设置为“LatLonProjection”，并添加LatLonProjection的设置。 请参阅[为嵌入投影信息中的图像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)。

* [为未投影图像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [要为嵌入投影信息中的图像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 为未投影图像指定LatLonProjection {#section-26554eefe645481faba68396fa13756a}

1. 在Data Workbench中打开[!DNL Terrain Images.cfg]文件，并添加地形图像层源，如[要定义地形图像层](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)中所述。

1. 参考以下参数表，编辑 Projection Info（投影信息）参数：

   | 参数 | 描述 |
   |---|---|
   | Lat0 | 图像顶部边缘的纬度（以度为单位），其中 90 表示北极，-90 表示南极。 |
   | Lat1 | 图像底部边缘的纬度。 |
   | Lon0 | 图像左侧边缘的经度（以度为单位），其中正数表示东经，负数表示西经。 |
   | Lon1 | 图像右侧边缘的经度。 |

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**&#x200B;并单击&#x200B;**[!UICONTROL Save]**&#x200B;保存文件。

1. 要将本地所做的更改保存到Data Workbench Server计算机，请在[!DNL Server Files Manager]中右键单击[!DNL Temp]列中[!DNL Terrain Images.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 为嵌入的投影信息{#section-174f4e00fad84a7ca0c995423dd37ae1}中的图像指定LatLonProjection

1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;视图其内容。 [!DNL Terrain Images.cfg] 文件位于此目录中。

1. 右键单击[!DNL Terrain Images.cfg]服务器名称列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Terrain Images.cfg]的[!DNL Temp]列中显示复选标记。

1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 [!DNL Terrain Images.cfg]文件显示在记事本窗口中。

1. 参考以下示例文件片段，编辑 Projection Info（投影信息）参数。请务必将投影类型指定为以下突出显示的内容。有关这些参数的描述，请参阅上一步骤中的“LatLonProjection 参数”表。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
