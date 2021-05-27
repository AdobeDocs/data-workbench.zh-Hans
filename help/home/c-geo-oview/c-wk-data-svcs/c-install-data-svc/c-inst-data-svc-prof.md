---
description: 数据服务配置文件（IP地理智能和IP地理位置）是为Adobe应用程序提供额外功能的内部配置文件。
title: 安装数据服务配置文件
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 3%

---

# 安装数据服务配置文件{#installing-the-data-service-profile}

数据服务配置文件（IP地理智能和IP地理位置）是为Adobe应用程序提供额外功能的内部配置文件。

与Adobe提供的所有其他内部用户档案一样，不应更改这些用户档案。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

数据服务配置文件包含以下要安装在Data Workbench Server上的数据集包含文件：

* **Profiles\*配置文件名称&#x200B;*\Dataset\Log Processing\Traffic\IP.cfg:**列出要从日志处理过程传递到转换的c-ip字段。
* **Profiles\*配置文件名称&#x200B;*\Dataset\Transformation\Geography\IPLookup.cfg:**定义一个IPLookup转换，该转换使用提供的IP地理智能或IP地理位置查找文件生成多个地理数据字段。

有关转换数据集包含文件的信息，请参阅《数据集配置指南》*。*

此外，每个数据服务配置文件还为您提供一个名为[!DNL IP Coordinates.layer]的元素点层文件。 此层文件允许您使用IP地址动态地映射数据集中在地球上的位置。 安装后，该层将存储在Data Workbench Server安装目录的Profiles\*data service name*\Maps文件夹中。

[!DNL IP Coordinates.layer]文件引用坐标维度，该维度在随[!DNL Geography]配置文件提供的[!DNL Coordinates.cfg]文件中定义，位于Dataset\Transformation\Geography folder文件夹中。 数据集中定义的“坐标”维度的每个元素都会使用该元素中包含的纬度和经度信息在地球上映射。 有关使用动态点的元素点层的更多信息，请参阅[定义使用动态点的元素点层](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

>[!NOTE]
>
>如果您安装了5.1版之前的IP地理智能和IP地理位置数据服务，则元素点层文件将引用一个查找文件，而不是使用动态点。 每个层文件都引用IP地理代码查找文件和IP地理代码维度。 IP地理代码查找文件包含IP地理代码（基于IP地址的地理位置）列表以及每个地理代码的纬度和经度。 数据集中定义的IP地理代码维度的每个元素都会使用IP地理代码查找文件中为该IP地理代码列出的经纬度在地球上进行映射。

每个数据服务的层文件名称及其引用的文件各不相同：

* [!DNL IP Geocodes D.layer]文件随IP地理情报(Digital Envoy)配置文件一起安装。 此元素点层引用[!DNL IP Geocodes D yyyymmdd.txt]查找文件（您需要定期更新）和IP地理代码D维度。

* [!DNL IP Geocodes Q.layer]文件随IP地理位置(Quova)配置文件一起安装。 此元素点层引用[!DNL IP Geocodes Q yyyymmdd.txt]查找文件（您需要定期更新）和IP地理代码Q维度。

有关使用查找文件的元素点层的更多信息，请参阅[定义引用查找文件的元素点层](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)。

## 安装IP地理智能或IP地理位置配置文件{#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>以下安装说明假定您已安装Data Workbench，并在Data Workbench与安装Data Workbench [!DNL Geography]的Data Workbench Server之间建立了连接。 如果尚未这样做，请参阅&#x200B;*Data Workbench用户指南*。

1. 从您从Adobe收到的[!DNL .zip]文件中打开Profiles文件夹。
1. 将IP地理智能或IP地理位置文件夹复制到Data Workbench Server安装目录的Profiles文件夹中。 您最终想要的是……\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example。 [!DNL Profiles]文件夹中其他文件夹的名称可能与显示的文件夹名称不同。

   ![](assets/Geo_installProfiles_dirIP.png)

1. 请按照以下步骤来更新要使用[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]配置文件的每个配置文件的[!DNL profile.cfg]文件。

   1. 打开 **[!UICONTROL Profile Manager]**.
   1. 右键单击[!DNL profile.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。

   1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，右键单击&#x200B;**[!UICONTROL Directories]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要将新目录添加到目录列表末尾，请右键单击列表中最后一个目录的编号或名称，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 键入新目录的名称：[!DNL IP Geo-intelligence]或I [!DNL P Geo-location]。

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL profile.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。

>[!NOTE]
>
>请勿将修改的配置文件保存到由Adobe提供的任何内部配置文件（包括[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]配置文件），因为当您安装这些配置文件的更新时，将覆盖您所做的更改。
