---
description: Insight Server的客户端（Report和Insight）使用通用名称来指代Insight Server。
title: 定义服务器的网络位置
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# 定义服务器的网络位置{#defining-the-server-s-network-location}

{{eol}}

Insight Server的客户端（Report和Insight）使用通用名称来指代Insight Server。

例如，当您连接 [!DNL Insight] 或 [!DNL Report] 到 [!DNL Insight Server]，则可以使用其通用名称来标识服务器(例如， [!DNL Server.MyCompany.com])。 在向服务器发送请求之前，客户端会在内部将通用名称解析为数字IP地址。

要将通用名称解析为IP地址， [!DNL Insight Server’s] 客户端使用名为地址文件的本地查找文件。 地址文件列出了 [!DNL Insight Servers] 安装，并标识其数字IP地址。 当客户在 [!DNL Insight Server].

当客户向 [!DNL Insight Server]，则会尝试通过地址文件解析服务器的通用名称。 如果地址文件标识所请求服务器的IP地址，则客户端将请求路由到指定的地址。 如果未定义地址（例如，地址文件未定义服务器的通用名称），则请求会失败。 或者，如果客户端的地址文件中未定义名称，则可以配置客户端，以通过操作环境的普通域命名服务(DNS)机制解析地址。 有关说明，请参阅 [NetworkLocation参数表](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) 在以下部分中。
