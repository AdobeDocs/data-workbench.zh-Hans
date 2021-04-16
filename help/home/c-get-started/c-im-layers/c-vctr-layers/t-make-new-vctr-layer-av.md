---
description: 使任何矢量层可在地球可视化上显示的步骤。
title: 使新矢量层可用
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 45%

---

# 使新矢量层可用{#make-a-new-vector-layer-available}

使任何矢量层可在地球可视化上显示的步骤。

1. 在用户档案服务器安装目录中的“用户档案名称”*\Maps文件夹中，放置图层文件和[!DNL .vec]或[!DNL .tsv]文件。
1. 编辑用户档案\*用户档案名称*\Maps文件夹中的[!DNL order.txt]文件，以反映您希望图层显示的顺序。 默认情况下，层会按其名称以词典顺序显示。

   >[!NOTE]
   >
   >编辑[!DNL order.txt]文件时，请注意不要覆盖要显示的映射图层。

   有关使用[!DNL order.txt]文件的详细信息，请参阅[使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

1. 在Insight中，通过右键单击工作区标题栏并单击&#x200B;**[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*&#x200B;来选择所需的用户档案。
1. 右键单击工作区标题栏，然后单击&#x200B;**[!UICONTROL Work Online]**。 随即会在“联机工作”旁边显示一个 X。
1. 打开一个工作区，然后在地球可视化上右键单击并选择新层。随即会在层名称旁边显示一个 X。
