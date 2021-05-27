---
description: 使新地形层可在地球可视化中显示的步骤。
title: 使新地形图像图层可用
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 25%

---

# 使新地形图像图层可用{#making-a-new-terrain-image-layer-available}

使新地形层可在地球可视化中显示的步骤。

1. 在&#x200B;**[!UICONTROL Insight Server]**&#x200B;安装目录的Profiles\*配置文件名称*\Maps文件夹中，放置层文件和支持的映像文件。
1. 编辑Profiles\*配置文件名称*\Maps文件夹中的[!DNL order.txt]文件，以反映您希望层的显示顺序。 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >编辑[!DNL order.txt]文件时，请注意不要覆盖要显示的映射层。

   有关使用[!DNL order.txt]文件的更多信息，请参阅《Data Workbench用户指南》*的“配置界面和分析功能”一章。*

1. 在Data Workbench中，右键单击工作区标题栏并单击&#x200B;**[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*，以选择所需的配置文件。
1. 右键单击工作区标题栏，然后单击&#x200B;**[!UICONTROL Work Online]**。 在[!DNL Work Online]旁边会显示一个X。
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
