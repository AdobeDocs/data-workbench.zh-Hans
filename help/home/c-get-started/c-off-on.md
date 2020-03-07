---
description: 有关脱机或联机使用Data Workbench Server的信息。
solution: Analytics
title: 脱机和联机工作
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Working offline and online{#working-offline-and-online}

有关脱机或联机使用Data Workbench Server的信息。

Data Workbench automatically downloads updates to the profile and its data from the Data Workbench server if you have a network connection to the [!DNL server] and are working online. 如果尚未指定联机工作，则Data Workbench会从计算机的缓存加载配置文件及其数据。 这种情况下，您查看的配置文件及其数据的版本是上次您使用配置文件联机工作时下载的版本。

脱机工作具有处理速度方面的优势，因为您是从本地缓存工作并且查询您自己计算机上的数据。联机工作时，每个查询都必须返回到Data Workbench Server，这需要更长的时间，并迫使您与其他联机用户争夺服务器资源。 只要您与Data Workbench Server有网络连接，脱机工作就会停止Data Workbench Server更新Data Workbench上的配置文件或数据，但不会停止将项目保存到Data Workbench Server。

由于能够脱机工作，因此Data Workbench Server的大小调整为可以处理数据集中一定数量的实时流量输入和一定数量的数据，以及一定数量的Data Workbench用户，但不必调整大小以支持最大数量的并发用户（实际上不经常发生）。 由于用户通常是查看趋势和比率、探究您使用的数据，因此大多数情况下您不需要精确的计数。如果需要使用当前数据进行查询并解析到精确的计数，则可以联机工作并获取此结果，但是查询将花费较长的时间才能解析到 100%。

**联机或脱机工作**

在侧栏中，单击设 **[!UICONTROL Connection]** 置并单击 **[!UICONTROL Work Online]**。

![](assets/sidebar_work_online.png)

在线工作时，Data Workbench将连接到Data Workbench服务器，并将您计算机上的信息与Data Workbench服务器上的配置文件及其数据集信息同步。

The default configuration for Data Workbench is to work offline, but as described in the following section, each user can change their [!DNL Insight.cfg] file to make their instance of Data Workbench work online by default.

**默认联机工作**

1. 导航到 Insight 安装目录。
1. 在文本编辑器中打开 [!DNL Insight.cfg] 文件。
1. 将突出显示的行添加到文件中，如以下示例所示：

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

下次打开Data Workbench时，它将连接到Data Workbench Server并默认联机工作。
