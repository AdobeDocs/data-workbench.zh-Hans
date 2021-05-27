---
description: 有关在Data Workbench Server上安装数据服务的信息。
title: 在 Data Workbench 服务器上安装数据服务
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# 在 Data Workbench 服务器上安装数据服务{#installing-a-data-service-on-a-data-workbench-server}

有关在Data Workbench Server上安装数据服务的信息。

如果您使用的是IP地理智能数据服务或IP地理位置数据服务，则必须在Data Workbench Server上安装[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]配置文件及相关的查找文件。 安装Data Workbench [!DNL Geography]配置文件后，必须完成以下步骤。 请参阅[安装Data Workbench地理](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)。 如果尚未安装Data Workbench，请按照&#x200B;*Data Workbench用户指南*&#x200B;中的说明进行操作，然后再继续。

>[!NOTE]
>
>要安装数据服务文件，您必须有权访问Data Workbench Server上的文件。

Adobe将IP地理智能和IP地理位置数据服务分发为[!DNL .zip]文件。 每个[!DNL .zip]文件都包含两个文件夹：查找和配置文件。 要在Data Workbench Server上安装数据服务，您必须执行以下步骤：

* 安装数据服务配置文件。 请参阅[安装数据服务配置文件](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md)。
* 安装数据服务查找。 请参阅[安装数据服务查找文件](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md)。

您必须在要处理和运行数据集配置文件的Data Workbench Server计算机上安装数据服务配置文件和查找文件。 如果您运行的是Data Workbench Server群集，则必须在主控服务器上安装文件。 有关数据集配置文件的信息，请参阅&#x200B;*《数据集配置指南》*。
