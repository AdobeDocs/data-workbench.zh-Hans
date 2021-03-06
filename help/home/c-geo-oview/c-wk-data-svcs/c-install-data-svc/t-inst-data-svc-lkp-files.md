---
description: 安装IP地理智能或IP地理位置查找文件的步骤。
title: 安装数据服务查找文件
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# 安装数据服务查找文件{#installing-the-data-service-lookup-files}

安装IP地理智能或IP地理位置查找文件的步骤。

随数据服务配置文件提供的查找文件(Lookups\*profile name*\*data file name*)是一个二进制文件([!DNL .bin])，其中包含基于IP地址的地理相关数据。 您必须定期替换此文件，以确保您拥有最新的地理数据。 请参阅[更新数据服务文件](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c)。

**安装IP地理情报或IP地理位置查找文件**

>[!NOTE]
>
>所有[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]数据文件都必须位于Data Workbench Server的可用物理内存中。

1. 从您从Adobe收到的[!DNL .zip]文件中打开Lookups文件夹。
1. 将IP地理智能或IP地理位置文件夹复制到Data Workbench Server安装目录的“查找”文件夹(您最终希望……\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example。 Lookups文件夹中其他文件夹的名称可能与显示的名称不同。

   ![步骤信息](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Adobe会定期向您发送包含更新的[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]查找文件的文件。 当您收到这些文件时，需要按照Adobe的指示，将它们加载到Data Workbench Server上。 有关说明，请参阅以下部分。
