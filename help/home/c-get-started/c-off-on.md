---
description: 有关脱机或联机使用Data Workbench服务器的信息。
title: 脱机工作和联机工作
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 32%

---

# 脱机工作和联机工作{#working-offline-and-online}

有关脱机或联机使用Data Workbench服务器的信息。

如果您与[!DNL server]有网络连接并且正在联机工作，Data Workbench会自动从Data Workbench服务器下载用户档案及其数据的更新。 如果未指定在线工作，Data Workbench将从计算机缓存加载用户档案及其数据。 这种情况下，您查看的配置文件及其数据的版本是上次您使用配置文件联机工作时下载的版本。

脱机工作具有处理速度方面的优势，因为您是从本地缓存工作并且查询您自己计算机上的数据。在线工作时，每个查询都必须返回Data Workbench服务器，这需要更长的时间，并会迫使您与其他在线用户争夺服务器资源。 只要您与Data Workbench服务器有网络连接，脱机工作就会阻止Data Workbench服务器更新Data Workbench上的用户档案或数据，但不会阻止您将项目保存到Data Workbench服务器。

由于能够脱机工作，Data Workbench服务器的大小可以处理数据集中某些实时流量输入和某些Data Workbench量，以及一些数据用户，但不必调整大小以支持最大数量的并发用户（实际上不经常发生）。 由于用户通常是查看趋势和比率、探究您使用的数据，因此大多数情况下您不需要精确的计数。如果需要使用当前数据进行查询并解析到精确的计数，则可以联机工作并获取此结果，但是查询将花费较长的时间才能解析到 100%。

**联机或脱机工作**

在侧栏中，单击&#x200B;**[!UICONTROL Connection]**&#x200B;设置，然后单击&#x200B;**[!UICONTROL Work Online]**。

![](assets/sidebar_work_online.png)

在线工作时，Data Workbench将连接到Data Workbench服务器，并将您计算机上的信息与Data Workbench服务器上的用户档案及其数据集信息同步。

Data Workbench的默认配置是脱机工作，但如下节所述，默认情况下，每个用户都可以更改其[!DNL Insight.cfg]文件，以使其Data Workbench实例联机工作。

**默认联机工作**

1. 导航到 Insight 安装目录。
1. 在文本编辑器中打开 [!DNL Insight.cfg] 文件。
1. 将突出显示的行添加到文件中，如以下示例所示：

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

下次打开Data Workbench时，它将连接到Data Workbench服务器，默认情况下在线工作。
