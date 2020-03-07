---
description: 使元素点层可在地球可视化上显示的步骤。
solution: Analytics
title: 使新元素点层可用
topic: Data workbench
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使新元素点层可用{#making-a-new-element-point-layer-available}

使元素点层可在地球可视化上显示的步骤。

1. 在Data Workbench Server安装目录的Profiles\*配置文件名称*\Maps文件夹中，放置层文件及其相关的查找文件。
1. 如果为元素点层定义了新维度，并且尚未重塑数据集，则将立即重塑数据集。
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   For more information about using [!DNL order.txt] files, see the Configuring Interface and Analysis Features chapter of the *Data Workbench User Guide*.

1. In data workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. X显示在旁边 [!DNL Work Online]。
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
