---
description: 数据服务配置文件（IP地理智能和IP地理位置）是内部配置文件，可为Adobe应用程序提供附加功能。
solution: Analytics
title: 安装数据服务配置文件
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装数据服务配置文件{#installing-the-data-service-profile}

数据服务配置文件（IP地理智能和IP地理位置）是内部配置文件，可为Adobe应用程序提供附加功能。

与Adobe提供的所有其他内部配置文件一样，不应更改这些配置文件。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

数据服务配置文件包括要安装在Data Workbench Server上的以下数据集包含文件：

* **配置文件\*配置文件名&#x200B;*称\Dataset\Log Processing\Traffic\IP.cfg:**列出要从日志处理传递到转换的c-ip字段。
* **配置文件\*配置文件名称&#x200B;*\Dataset\Transformation\Geography\IPLookup.cfg:**定义一个IPLookup转换，该转换使用提供的IP地理智能或IP地理位置查找文件生成多个地理数据字段。

For information about transformation dataset include files, see the *Dataset Configuration Guide*.

此外，每个数据服务配置文件还为您提供一个名为的元素点层文件 [!DNL IP Coordinates.layer]。 此层文件允许您使用IP地址动态地映射数据集中地球上的位置。 安装后，该层存储在Data Workbench Server安装目录的Profiles\*data service name*\Maps文件夹中。

该文 [!DNL IP Coordinates.layer] 件引用“坐标”(Coordinates)尺寸，该尺寸在随配置文件提供的 [!DNL Coordinates.cfg] 文件中定义， [!DNL Geography] 并位于Dataset\Transformation\Geography folder文件夹中。 在数据集中定义的“坐标”维的每个元素都会使用元素中包含的纬度和经度信息映射到地球上。 有关使用动态点的元素点层的详细信息，请参阅 [使用动态点定义元素点层](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

>[!NOTE]
>
>如果您在5.1版之前安装了IP地理智能和IP地理位置数据服务，则元素点层文件将引用查找文件，而不是使用动态点。 每个层文件都引用IP Geocodes查找文件和IP Geocode维。 IP地理代码查找文件包含IP地理代码（基于IP地址的地理位置）列表以及每个地理代码的纬度和经度。 数据集中定义的IP地理代码维度的每个元素都会使用在IP地理代码查找文件中为该IP地理代码列出的经纬度映射到地球上。

层文件的名称及其引用的文件对于每个数据服务而言都不同：

* 该文件 [!DNL IP Geocodes D.layer] 随IP Geo-intelligence(Digital Envoy)配置文件一起安装。 此元素点层引用 [!DNL IP Geocodes D yyyymmdd.txt] 查找文件（您需要定期更新）和IP Geocode D维。

* 文件 [!DNL IP Geocodes Q.layer] 随IP地理位置(Quova)配置文件一起安装。 此元素点层引用 [!DNL IP Geocodes Q yyyymmdd.txt] 查找文件（您需要定期更新）和IP Geocode Q维。

有关使用查找文件的元素点层的详细信息，请参阅定 [义元素点层引用查找文件](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)。

## 安装IP地理智能或IP地理位置配置文件的步骤 {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>以下安装说明假定您已安装Data Workbench，并在Data Workbench与要安装Data Workbench的Data Workbench Server之间建立了连接 [!DNL Geography]。 如果尚未执行此操作，请参阅《 *Data Workbench用户指南》*。

1. 从您从Adobe收到的文 [!DNL .zip] 件中打开Profiles文件夹。
1. 将IP Geo-intelligence或IP Geo-location文件夹复制到Data Workbench Server安装目录的Profiles文件夹中。 你最终想得到……\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example。 文件夹中其他文件夹的名称 [!DNL Profiles] 可能与显示的文件夹不同。

   ![](assets/Geo_installProfiles_dirIP.png)

1. 请按照以下步骤为要使用 [!DNL profile.cfg] 该或配置文件的每个配置文件更新 [!DNL IP Geo-intelligence] 文件 [!DNL IP Geo-location] 。

   1. 打开 **[!UICONTROL Profile Manager]**.
   1. 右键单击旁边的复选标记， [!DNL profile.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 The [!DNL profile.cfg] window appears.

   1. 在窗 [!DNL profile.cfg]口中，右键单击并 **[!UICONTROL Directories]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要将新目录添加到目录列表的末尾，请右键单击列表中最后一个目录的编号或名称，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 键入新目录的名称：或 [!DNL IP Geo-intelligence] 者我 [!DNL P Geo-location]。

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在列 [!DNL Profile Manager]中，右键单击列中的复 [!DNL profile.cfg] 选 [!DNL User] 标记，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

>[!NOTE]
>
>Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] profile), as your changes are overwritten when you install updates to these profiles.

