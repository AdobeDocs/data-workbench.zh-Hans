---
description: 检查收集器是否正在使用不同的方法运行。
title: 确认数据收集器正在运行
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# 确认数据收集器正在运行{#confirming-that-the-data-collector-is-running}

检查收集器是否正在使用不同的方法运行。

**推荐频率：** 每5-10分钟

* [在发送器中使用站点测试功能。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [检查 [!DNL Sensor] 是否正在设置Cookie。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## 使用站点测试{#section-a5a697c3252e40f184c0b662926170f2}

验证收集器是否正在运行的一种方法是，在发送器中启用“站点测试”功能。 启用站点测试时，发送器会定期（每60秒）向运行收集器的Web服务器发送GET请求。 如果Site Test未从Web服务器获得响应，它会向syslog写入错误消息，并向[!DNL data workbench server]（将写入传感器日志文件）发送错误消息。

如果站点测试收到来自Web服务器的响应，则它在队列文件中查找来自Web服务器的数据包。 如果数据包未显示（表示收集器未运行以捕获事件），则Site Test会向syslog写入错误消息，并向Adobe发送错误消息（也会写入传感器日志文件）。

在站点测试向Web服务器发送的请求中，站点测试将用户代理值设置为“ [!DNL Sensor]测试”。 如果您不希望这些请求显示在数据集中，请将“ [!DNL Sensor] Test&quot; User-Agent添加到[!DNL Baseline Robots List.txt]文件或[!DNL data workbench server]文件夹[!DNL Lookups]文件夹的[!DNL Extended Robots List.txt]文件中。

**在发送器中启用站点测试**

1. 在运行[!DNL Sensor]的计算机上找到[!DNL txlogd.conf]文件，并在文本编辑器中将其打开。

1. 在[!DNL txlogd.conf]文件中，找到“SiteTest”行并对其进行配置，如下所示。 如果您的[!DNL txlogd.conf]文件不包含“SiteTest”行，只需将该行添加到配置文件的末尾即可。

   SiteTest http， *serverAddress*, *port*, *resource*

   其中，*serverAddress*&#x200B;是Web服务器的名称或IP地址，*port*&#x200B;是服务器的HTTP侦听端口，而&#x200B;*resource*&#x200B;是您希望Site Test在测试服务器时请求的特定资源。 请注意，*resource*&#x200B;可以包含查询字符串。

   示例：SiteTest http，localhost，80,/index.jsp

   要测试多个Web服务器，只需指定多条SiteTest行。

## 检查Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

验证收集器是否在Web服务器上运行的另一种方法是检查[!DNL Sensor]是否在Web服务器返回到客户端的响应中设置Cookie。 如果收集器工作，则Web服务器会返回“v1st”Cookie。

可以重命名Cookie。 如果已经这样做，则必须查找指定的名称，而不是v1st。

您可以使用自动脚本或监视代理执行此检查。 有关此任务的示例脚本或其他帮助，请联系Adobe咨询服务。
