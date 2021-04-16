---
description: Insight Server的客户端(Report and Insight)使用通用名称引用Insight Server。
title: 定义服务器的网络位置
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# 定义服务器的网络位置{#defining-the-server-s-network-location}

Insight Server的客户端(Report and Insight)使用通用名称引用Insight Server。

例如，将[!DNL Insight]或[!DNL Report]连接到[!DNL Insight Server]时，可以使用其通用名称（例如[!DNL Server.MyCompany.com]）来标识服务器。 在内部，客户端在向服务器发送请求之前将通用名称解析为数字IP地址。

要将通用名称解析为IP地址，[!DNL Insight Server’s]客户端使用名为地址文件的本地查找文件。 地址文件列表了您组织中安装的[!DNL Insight Servers]的公用名称，并标识其数字IP地址。 当客户端在[!DNL Insight Server]上打开用户档案时，会自动接收地址文件的副本。

当客户端向[!DNL Insight Server]发出请求时，它会尝试通过地址文件解析服务器的公用名称。 如果地址文件标识所请求服务器的IP地址，则客户端将请求路由到指定地址。 如果未定义地址（例如，地址文件未定义服务器的公用名称），则请求将失败。 或者，如果客户端的地址文件中未定义名称，您可以配置客户端，以通过操作环境的常规域命名服务(DNS)机制解析地址。 有关说明，请参阅下一节[NetworkLocation Parameters表](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05)中的Parent参数。
