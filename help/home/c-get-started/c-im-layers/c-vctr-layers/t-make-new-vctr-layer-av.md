---
description: 使任何矢量层可在地球可视化上显示的步骤。
title: 使新矢量图层可用
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 45%

---

# 使新矢量图层可用{#make-a-new-vector-layer-available}

{{eol}}

使任何矢量层可在地球可视化上显示的步骤。

1. 在Data Workbench服务器安装目录的Profiles\*配置文件名称*\Maps文件夹中，放置层文件和 [!DNL .vec] 或 [!DNL .tsv] 文件。
1. 编辑 [!DNL order.txt] 文件，以反映您希望层的显示顺序。 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >编辑 [!DNL order.txt] 文件中，请注意不要覆盖要显示的映射层。

   有关使用的更多信息 [!DNL order.txt] 文件，请参阅 [使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. 在Insight中，右键单击工作区标题栏并单击，以选择所需的配置文件 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. 右键单击工作区标题栏，然后单击 **[!UICONTROL Work Online]**. 随即会在“联机工作”旁边显示一个 X。
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
