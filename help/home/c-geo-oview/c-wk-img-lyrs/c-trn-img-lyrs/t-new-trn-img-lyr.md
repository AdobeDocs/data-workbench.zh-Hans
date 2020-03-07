---
description: 使新的地形层可在地球可视化上显示的步骤。
solution: Analytics
title: 使新地形图像层可用
topic: Data workbench
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使新地形图像层可用{#making-a-new-terrain-image-layer-available}

使新的地形层可在地球可视化上显示的步骤。

1. In the Profiles\*profile name*\Maps folder within the **[!UICONTROL Insight Server]** installation directory, place the layer file and the supporting image files.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   For more information about using [!DNL order.txt] files, see the Configuring Interface and Analysis Features chapter of the *Data Workbench User Guide*.

1. In data workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. X显示在旁边 [!DNL Work Online]。
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
