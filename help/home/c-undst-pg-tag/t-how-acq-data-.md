---
description: 您必须在为站点提供内容的每台Web服务器上安装并运行传感器，以收集这些服务器看到的所有请求。
solution: Analytics
title: 如何获取此数据_
topic: Data workbench
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 如何获取此数据_{#how-do-i-acquire-this-data}

您必须在为站点提供内容的每台Web服务器上安装并运行传感器，以收集这些服务器看到的所有请求。

这些请求占对您网站提出的请求的90%或以上，以及完整分析网站流量所需的90%或以上数据。 [!DNL Page Tags] 然后，应用于收集Web服务器未知的其余10%或更少流量数据。 但是，根据我们的运营经验，以下是从您的站点收集Web请求数据的有效配置（按优先顺序排列）:

1. [!DNL Sensor] 安装在您控制并支持您的站点的每台Web服务器上。 应标记来自第三方站点的内容、从缓存提供的内容以及某些类型的动态内容，并且此类页面标记应将他们收集的数据发送到您正在运行的位置的Web服务器 [!DNL Sensor]。 如果页面标记请求流量的级别合理，或在特殊情况下，专用Web服务器来收集这些页面标记请求，则可以添加额外的Web服务器。
1. [!DNL Sensor] 安装在您专用于从标记页面收集页面标记请求数据的位置的两台Web服务器上（本指南中也称为数据收集服务器）。 站点上的所有内容都已标记，并且所有页面标记都定向到两个数据收集服务器。
1. [!DNL Sensor’s] 数据收集服务由运行数据收集服务器以收集您的所有Web请求数据的外部源提供。 在这种情况下，站点上的所有内容都会被标记，并且页面标记会将其数据发送到外包数据收集服务器。

   For more information about [!DNL Sensor], see the *Data Workbench[!DNL Sensor]Guide*.

