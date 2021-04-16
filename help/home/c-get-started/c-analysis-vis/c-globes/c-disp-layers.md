---
description: “地域”配置文件存储图像层和文件的集合。
title: 显示图层
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 69%

---

# 显示图层{#display-layers}

“地域”配置文件存储图像层和文件的集合。

显示地球时，可以选择要为特殊分析任务显示的可用层：

* **蓝色大理石 2km：**&#x200B;该层显示地球。当未选择该层时，地球不可见。
* **IP 坐标：**&#x200B;该元素点层基于访客 IP 地址显示数据集中位置的纬度和经度。
* **邮政编码点：**&#x200B;该层基于 Adobe 提供的美国邮政编码列表显示数据集中位置的纬度和经度。[!DNL Zip Points.txt] 查找文件包含要显示的邮政编码、纬度和经度数据，而 [!DNL Zip Points.layer] 文件则包含在地球上显示此数据所需的配置参数。这两个文件都存储在Profiles\Geography\Maps folder within the Data Workbench server installation directory文件夹中。

* ***其他可用的图层名*** 称：每个图 [!DNL .layer] 层名称都表示存储在Profiles\Geography\Maps folder文件夹、用户档案\IP Geo-location\Maps文件夹或Insight Server安装目录中的用户档案\IP Geo-intelligence\Maps文件夹中的文件。

>[!NOTE]
>
>要获得IP地理位置或IP地理智能用户档案，您必须分别订阅IP地理位置或IP地理智能数据服务。

若要控制层的显示顺序，可以使用 [!DNL order.txt] 文件。请参阅[使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

**切换地球中的层**

* 右键单击可视化，然后单击所需的层名称。层左侧的 X 表示该层可见。
