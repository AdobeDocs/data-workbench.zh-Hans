---
description: 使元素点层可用于在地球可视化图表上显示的步骤。
title: 使新元素点层可用
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 33%

---

# 使新元素点层可用{#making-a-new-element-point-layer-available}

{{eol}}

使元素点层可用于在地球可视化图表上显示的步骤。

1. 在Data Workbench Server安装目录的Profiles\*配置文件名称*\Maps文件夹中，放置层文件及其相关的查找文件。
1. 如果为元素点层定义了新维度，并且尚未重塑数据集，则将立即重塑数据集。
1. 编辑 [!DNL order.txt] 文件，以反映您希望层的显示顺序。 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >编辑 [!DNL order.txt] 文件中，请注意不要覆盖要显示的映射层。

   有关使用的更多信息 [!DNL order.txt] 文件，请参阅 *Data Workbench用户指南*.

1. 在Data Workbench中，右键单击工作区标题栏并单击，以选择所需的配置文件 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. 右键单击工作区标题栏，然后单击 **[!UICONTROL Work Online]**. X显示在 [!DNL Work Online].
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
