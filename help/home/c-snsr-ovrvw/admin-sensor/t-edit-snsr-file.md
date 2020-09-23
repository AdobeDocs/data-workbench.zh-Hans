---
description: 传感器配置文件txlogd.conf包含传感器用来建立与Data Workbench Server连接的参数。
solution: Analytics
title: 编辑传感器 txlogd.conf 文件
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 7%

---


# 编辑传感器 txlogd.conf 文件{#editing-the-sensor-txlogd-conf-file}

传感器配置文件txlogd.conf包含传感器用来建立与Data Workbench Server连接的参数。

这些参数包括服务器的地址、端口号和通信协议（HTTP或HTTPS）。 配置文件还包含日志内容过滤选项和受控实验信息。 受控实验使站点设计人员能够对所有站点访客的子集进行测试或设计更改。

更改其 [!DNL txlogd.conf] 他参数(如IP地 [!DNL data workbench server] 址或名称 [!DNL Sensor])时，您可能只需用更新后的版 [!DNL txlogd.conf] 本进行替换，并 [!DNL Sensor] 自动获取更改。 在某些系统上，如果不停止Web服务器或发射器进程，则可能无法编辑或替换文件。

**打开和编辑txlogd.conf**

1. 浏览到安 [!DNL Sensor] 装目录，在文本 [!DNL txlogd.conf] 编辑器中打开文件。
1. 根据需要编辑文件。
1. 保存并关闭该文件。

   * 受控实验配置文件(由文件中的ExpFile参数定义 [!DNL txlogd.conf] )的位置应位于Web服务器上的一个目录中，供Web内容开发人员访问或由内容管理系统控制。
   * ExpCookieURL参数中的值是用于测试网站的虚拟页。 访问该页面的用户将获得新的跟踪ID。

有关使用的更多信 [!DNL txlogd.conf]息，请联系Adobe咨询服务。
