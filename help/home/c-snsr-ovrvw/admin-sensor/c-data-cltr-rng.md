---
description: 检查收集器是否使用不同的方法运行。
solution: Analytics
title: 确认数据收集器正在运行
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---


# 确认数据收集器正在运行{#confirming-that-the-data-collector-is-running}

检查收集器是否使用不同的方法运行。

**推荐频率：** 每5-10分钟

* [在发射器中使用站点测试功能。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [检 [!DNL Sensor] 查是否设置Cookie。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## 使用站点测试 {#section-a5a697c3252e40f184c0b662926170f2}

验证收集器是否正在运行的一种方法是在发射器中启用“Site Test（现场测试）”功能。 启用“站点测试”时，发射器会定期（每60秒）向运行收集器的Web服务器发送GET请求。 如果站点测试未从Web服务器获得响应，它将错误消息写入syslog，并将错误消息发送 [!DNL data workbench server] 到（写入传感器日志文件）。

如果站点测试收到来自Web服务器的响应，它会在队列文件中查找来自Web服务器的数据包。 如果未显示事件包(表示收集器未运行以捕获Adobe)，站点测试会将错误消息写入syslog并向发送错误消息（也写入传感器日志文件）。

在站点测试发送到Web服务器的请求中，站点测试将用户代理值设置为“ [!DNL Sensor] 测试”。 如果您不希望这些请求显示在数据集中，请将“ [!DNL Sensor] Test” User-Agent添加 [!DNL Baseline Robots List.txt] 到文件 [!DNL Extended Robots List.txt] 或文件夹 [!DNL Lookups] 中的文件 [!DNL data workbench server]。

**在发射器中启用站点测试**

1. 在运行 [!DNL txlogd.conf] 时所在的计算机上找 [!DNL Sensor] 到该文件，并在文本编辑器中将其打开。

1. 在文 [!DNL txlogd.conf] 件中，找到“SiteTest”行并进行如下配置。 如果 [!DNL txlogd.conf] 您的文件不包含“SiteTest”行，只需将该行添加到配置文件的末尾。

   SiteTest http, *serverAddress*, *port*，资 *源*

   其 *中* , serverAddress是Web服务器的名称或IP地址， *port是服务器的HTTP侦听端口，* resource ** 是测试服务器时希望“站点测试”请求的特定资源。 请注意 *，资源* 可以包含查询字符串。

   示例：SiteTest http,localhost,80,/index.jsp

   要测试多个Web服务器，只需指定多个SiteTest行。

## 检查Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

验证收集器是否正在Web服务器上运行的另一种方法是检查 [!DNL Sensor] 是否在Web服务器返回给客户端的响应中设置Cookie。 如果收集器正在工作，则Web服务器返回“v1st” cookie。

可以重命名Cookie。 如果您已这样做，则必须查找指定的名称，而不是v1st。

您可以使用自动脚本或监视代理执行此检查。 有关此任务的示例脚本或其他帮助，请与Adobe咨询服务联系。
