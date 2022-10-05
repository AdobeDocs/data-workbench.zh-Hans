---
description: 使矢量层可用于在地球可视化图表上显示的步骤。
title: 使新矢量图层可用
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 24%

---

# 使新矢量图层可用{#making-a-new-vector-layer-available}

{{eol}}

使矢量层可用于在地球可视化图表上显示的步骤。

1. 在Data Workbench Server安装目录的Profiles\*配置文件名称*\Maps文件夹中，放置层文件和 [!DNL .vec] 或 [!DNL .tsv] 文件。
1. 编辑 [!DNL order.txt] 文件，以反映您希望层的显示顺序。 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >编辑 [!DNL order.txt] 文件中，请注意不要覆盖要显示的映射层。

   有关使用的更多信息 [!DNL order.txt] 文件，请参阅 *Data Workbench用户指南*.

1. 在Data Workbench中，右键单击工作区标题栏并单击，以选择所需的配置文件 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. 右键单击工作区标题栏，然后单击 **[!UICONTROL Work Online]**. X显示在 [!DNL Work Online].
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
