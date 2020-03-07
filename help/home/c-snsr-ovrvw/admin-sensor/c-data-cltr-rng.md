---
description: 检查收集器是否使用不同的方法运行。
solution: Insight
title: 确认数据收集器正在运行
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 确认数据收集器正在运行{#confirming-that-the-data-collector-is-running}

检查收集器是否使用不同的方法运行。

**推荐频率：** 每5-10分钟

* [使用发射器中的站点测试功能。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [检查[!DNL传感器]是否在设置cookie。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## 使用站点测试 {#section-a5a697c3252e40f184c0b662926170f2}

验证收集器是否正在运行的一种方法是在发射器中启用“Site Test”（现场测试）功能。 启用“站点测试”后，发射器会定期（每60秒）向运行收集器的Web服务器发送GET请求。 如果Site Test未从Web服务器获得响应，它会向syslog写入错误消息并向 [!DNL data workbench server] （写入传感器日志文件）发送错误消息。

如果“站点测试”从Web服务器收到响应，则它在队列文件中查找来自Web服务器的数据包。 如果未显示该数据包（表示收集器未运行以捕获事件）,Site Test会向syslog写入错误消息，并向Adobe发送错误消息（也会写入传感器日志文件）。

在站点测试发送到Web服务器的请求中，站点测试将User-Agent值设置为“ [!DNL Sensor] 测试”。如果您不希望这些请求显示在数据集中，请将“ [!DNL Sensor] Test” User-Agent添加到文件中， [!DNL Baseline Robots List.txt] 或将 [!DNL Extended Robots List.txt] User-Agent添加到 [!DNL Lookups] 文件夹中 [!DNL data workbench server]。

**在发射器中启用站点测试**

1. 在运行 [!DNL txlogd.conf] 时所在的计算机上找 [!DNL Sensor] 到该文件，然后在文本编辑器中将其打开。

1. 在文 [!DNL txlogd.conf] 件中，找到“SiteTest”行并进行配置，如下所示。 如果文 [!DNL txlogd.conf] 件不包含“SiteTest”行，只需将该行添加到配置文件的末尾。

   SiteTest http, *serverAddress*, *port*, resource **

   其中 *serverAddress* 是Web服务器的名称或IP地址，port ** 是服务器的HTTP监听端口， *resource* 是测试服务器时希望Site Test请求的特定资源。 请注意 ** ，资源可以包含查询字符串。

   示例：SiteTest http,localhost,80,/index.jsp

   要测试多台Web服务器，只需指定多条SiteTest行。

## 检查Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

验证收集器是否正在Web服务器上运行的另一种方法是检查是否在Web服 [!DNL Sensor] 务器返回给客户端的响应中设置Cookie。 如果收集器正在工作，Web服务器将返回“v1st”Cookie。

可以重命名Cookie。 如果您已经这样做，则必须查找指定的名称，而不是v1st。

您可以使用自动脚本或监视代理执行此检查。 有关此任务的示例脚本或其他帮助，请与Adobe咨询服务部门联系。
