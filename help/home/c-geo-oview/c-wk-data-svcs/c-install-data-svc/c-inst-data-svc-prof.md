---
description: 数据服务用户档案（IP地理智能和IP地理位置）是为您的Adobe应用程序提供附加功能的内部用户档案。
title: 安装数据服务配置文件
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 3%

---

# 安装数据服务配置文件{#installing-the-data-service-profile}

数据服务用户档案（IP地理智能和IP地理位置）是为您的Adobe应用程序提供附加功能的内部用户档案。

与Adobe提供的所有其他内部用户档案一样，不应更改这些用户档案。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

数据服务用户档案包括要安装在Data Workbench Server上的以下数据集包含文件：

* **用户档案\*用户档案名&#x200B;*称\Dataset\Log Processing\Traffic\IP.cfg*:*将要从日志处理传递到转换的c-ip字段列表。
* **用户档案\*用户档案名&#x200B;*称\Dataset\Transformation\Geography\IPLookup.cfg:**定义一个IPLookup转换，它使用提供的IP地理智能或IP地理位置查找文件生成多个地理数据字段。

有关转换数据集包含文件的信息，请参阅&#x200B;*Dataset Configuration Guide*。

此外，每个数据服务用户档案都为您提供一个名为[!DNL IP Coordinates.layer]的元素点层文件。 此图层文件允许您使用IP地址动态地映射数据集中在地球上的位置。 安装后，该层存储在Data Workbench Server安装目录中的“用户档案”\*数据服务名称*\Maps文件夹中。

[!DNL IP Coordinates.layer]文件引用Coordinates维度，该维度在随[!DNL Geography]用户档案提供的[!DNL Coordinates.cfg]文件中定义，位于Dataset\Transformation\Geography folder文件夹中。 在数据集中定义的每个坐标维度元素都将使用该元素中包含的纬度和经度信息映射到地球。 有关使用动态点的元素点图层的详细信息，请参阅[使用动态点定义元素点图层](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

>[!NOTE]
>
>如果您在5.1版之前安装了IP地理智能和IP地理位置数据服务，则您的元素点层文件将引用一个查找文件，而不是使用动态点。 每个层文件都引用IP Geocodes查找文件和IP Geocode维。 IP地理码查找文件包含IP地理码列表（基于IP地址的地理位置）以及每个地理码的纬度和经度。 数据集中定义的IP Geocode维度的每个元素都会使用IP Geocodes查找文件中为该IP Geocode列出的经纬度映射到地球。

图层文件的名称及其引用的文件对于每个数据服务都不同：

* [!DNL IP Geocodes D.layer]文件随IP Geo-intelligence(Digital Envoy)用户档案一起安装。 此元素点层引用[!DNL IP Geocodes D yyyymmdd.txt]查找文件（需要定期更新）和IP Geocode D维度。

* [!DNL IP Geocodes Q.layer]文件随IP地理位置(Quova)用户档案一起安装。 此元素点层引用[!DNL IP Geocodes Q yyyymmdd.txt]查找文件（需要定期更新）和IP Geocode Q维度。

有关使用查找文件的元素点图层的详细信息，请参阅[定义元素点图层引用查找文件](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)。

## 安装IP地理信息或IP地理位置用户档案{#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>以下安装说明假定您已安装Data Workbench，并已在Data Workbench与要安装Data Workbench [!DNL Geography]的Data Workbench Server之间建立连接。 如果尚未这样做，请参阅&#x200B;*《Data Workbench用户指南》*。

1. 从您从用户档案收到的[!DNL .zip]文件中打开Adobe文件夹。
1. 将IP Geo-intelligence或IP Geo-location文件夹复制到Data Workbench Server安装目录中的用户档案文件夹。 你最终想得到……\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example。 [!DNL Profiles]文件夹中其他文件夹的名称可能与显示的文件夹不同。

   ![](assets/Geo_installProfiles_dirIP.png)

1. 请按照以下步骤为要使用[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]用户档案的每个用户档案更新[!DNL profile.cfg]文件。

   1. 打开 **[!UICONTROL Profile Manager]**.
   1. 右键单击[!DNL profile.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 此文件的复选标记显示在[!DNL User]列中。

   1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，右键单击&#x200B;**[!UICONTROL Directories]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要将新目录添加到目录列表的末尾，请右键单击列表中最后一个目录的编号或名称，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 键入新目录的名称：[!DNL IP Geo-intelligence]或I [!DNL P Geo-location]。

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL profile.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

>[!NOTE]
>
>请勿将修改后的配置文件保存到Adobe提供的任何内部用户档案(包括[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]用户档案)，因为当您安装这些用户档案的更新时，您所做的更改会被覆盖。
