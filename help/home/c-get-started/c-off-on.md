---
description: 有关脱机或联机使用Data Workbench服务器的信息。
title: 脱机工作和联机工作
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 32%

---

# 脱机工作和联机工作{#working-offline-and-online}

{{eol}}

有关脱机或联机使用Data Workbench服务器的信息。

如果您拥有与 [!DNL server] 和在线工作。 如果未指定联机工作，则Data Workbench会从计算机的缓存中加载配置文件及其数据。 这种情况下，您查看的配置文件及其数据的版本是上次您使用配置文件联机工作时下载的版本。

脱机工作具有处理速度方面的优势，因为您是从本地缓存工作并且查询您自己计算机上的数据。联机工作时，每个查询都必须返回到Data Workbench服务器，这会花费较长的时间，并强制您与其他联机用户竞争服务器资源。 只要您与Data Workbench服务器有网络连接，脱机工作就会阻止Data Workbench服务器更新您Data Workbench上的配置文件或数据，但不会阻止将项目保存到Data Workbench服务器。

由于能够脱机工作，因此Data Workbench服务器的大小可以处理一定数量的实时流量输入和数据集中一定数量的Data Workbench，以及一定数量的客户用户，但不必调整大小以支持最大数量的并发用户（实际上并不经常出现）。 由于用户通常是查看趋势和比率、探究您使用的数据，因此大多数情况下您不需要精确的计数。如果需要使用当前数据进行查询并解析到精确的计数，则可以联机工作并获取此结果，但是查询将花费较长的时间才能解析到 100%。

**联机或脱机工作**

在侧栏中，单击 **[!UICONTROL Connection]** 设置并单击 **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

联机工作时，Data Workbench会连接到Data Workbench服务器，并将计算机上的信息与Data Workbench服务器上的配置文件及其数据集信息同步。

Data Workbench的默认配置是脱机工作，但如以下部分所述，每个用户都可以更改其 [!DNL Insight.cfg] 文件以使其Data Workbench实例默认联机。

**默认联机工作**

1. 导航到 Insight 安装目录。
1. 在文本编辑器中打开 [!DNL Insight.cfg] 文件。
1. 将突出显示的行添加到文件中，如以下示例所示：

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

下次打开Data Workbench时，它会连接到Data Workbench服务器并默认联机工作。
