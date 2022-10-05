---
description: 使新地形层可在地球可视化中显示的步骤。
title: 使新地形图像图层可用
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 25%

---

# 使新地形图像图层可用{#making-a-new-terrain-image-layer-available}

{{eol}}

使新地形层可在地球可视化中显示的步骤。

1. 在 **[!UICONTROL Insight Server]** 安装目录，放置层文件和支持映像文件。
1. 编辑 [!DNL order.txt] 文件，以反映您希望层的显示顺序。 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >编辑 [!DNL order.txt] 文件中，请注意不要覆盖要显示的映射层。

   有关使用的更多信息 [!DNL order.txt] 文件，请参阅 *Data Workbench用户指南*.

1. 在Data Workbench中，右键单击工作区标题栏并单击，以选择所需的配置文件 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. 右键单击工作区标题栏，然后单击 **[!UICONTROL Work Online]**. X显示在 [!DNL Work Online].
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
