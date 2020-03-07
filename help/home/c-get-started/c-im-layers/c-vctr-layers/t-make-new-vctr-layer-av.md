---
description: 使任何矢量层可在地球可视化上显示的步骤。
solution: Analytics
title: 使新的矢量图层可用
topic: Data workbench
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Make a new vector layer available{#make-a-new-vector-layer-available}

使任何矢量层可在地球可视化上显示的步骤。

1. In the Profiles\*profile name*\Maps folder within the Data Workbench server installation directory, place the layer file and the [!DNL .vec] or [!DNL .tsv] files.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   有关使用文件的更 [!DNL order.txt] 多信息，请参 [阅使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

1. In Insight, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. 随即会在“联机工作”旁边显示一个 X。
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
