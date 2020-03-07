---
description: Insight Server的客户端(Report and Insight)使用通用名称来引用Insight Server。
solution: Insight
title: 定义服务器的网络位置
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定义服务器的网络位置{#defining-the-server-s-network-location}

Insight Server的客户端(Report and Insight)使用通用名称来引用Insight Server。

例如，当您连接或 [!DNL Insight] 连接到 [!DNL Report] 服务器 [!DNL Insight Server]时，您使用其通用名称(例如， [!DNL Server.MyCompany.com])来标识服务器。 在内部，客户端将通用名称解析为数字IP地址，然后向服务器发送请求。

要将通用名称解析为IP地址，客 [!DNL Insight Server’s] 户端使用称为地址文件的本地查找文件。 地址文件列出了单位安装的 [!DNL Insight Servers] 通用名称，并标识其数字IP地址。 客户端在上打开配置文件时会自动接收地址文件的副本 [!DNL Insight Server]。

当客户端向某个发出请求 [!DNL Insight Server]时，它会尝试通过地址文件解析服务器的通用名称。 如果地址文件标识所请求服务器的IP地址，则客户端将请求路由到指定的地址。 如果未定义地址（例如，地址文件未定义服务器的通用名称），则请求将失败。 或者，如果客户端的地址文件中未定义名称，您也可以配置客户端，以通过操作环境的常规域命名服务(DNS)机制解析地址。 有关说明，请参阅下一节“NetworkLocation参数”表 [中的“父项](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) ”参数。
