---
description: 有关在Data Workbench Server上安装Data Service的信息。
title: 在 Data Workbench 服务器上安装数据服务
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# 在 Data Workbench 服务器上安装数据服务{#installing-a-data-service-on-a-data-workbench-server}

有关在Data Workbench Server上安装Data Service的信息。

如果您使用IP Geo-intelligence数据服务或IP Geo-location数据服务，则必须在Data Workbench Server上安装[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]用户档案以及相关的查找文件。 安装Data Workbench [!DNL Geography]用户档案后，必须完成以下过程。 请参阅[安装Data Workbench地理](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)。 如果尚未安装Data Workbench，请按照&#x200B;*《Data Workbench用户指南》*&#x200B;中的说明操作，然后再继续。

>[!NOTE]
>
>要安装Data Service文件，您必须有权访问Data Workbench Server上的文件。

Adobe将IP地理智能和IP地理位置数据服务分发为[!DNL .zip]文件。 每个[!DNL .zip]文件包含两个文件夹：查找和用户档案。 要在Data Workbench Server上安装数据服务，必须执行以下步骤：

* 安装数据服务用户档案。 请参阅[安装数据服务用户档案](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md)。
* 安装数据服务查找。 请参阅[安装数据服务查找文件](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md)。

您必须在要处理并运行数据集用户档案的Data Workbench Server计算机上安装Data Service用户档案和查找文件。 如果运行的是Data Workbench Server群集，则必须在主控服务器上安装文件。 有关数据集用户档案的信息，请参阅&#x200B;*Dataset Configuration Guide*。
