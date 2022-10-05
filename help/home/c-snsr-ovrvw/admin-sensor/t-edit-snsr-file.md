---
description: 传感器配置文件txlogd.conf包含传感器用来与Data Workbench Server建立连接的参数。
title: 编辑传感器 txlogd.conf 文件
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 7%

---

# 编辑传感器 txlogd.conf 文件{#editing-the-sensor-txlogd-conf-file}

{{eol}}

传感器配置文件txlogd.conf包含传感器用来与Data Workbench Server建立连接的参数。

这些参数包括服务器的地址、端口号和通信协议（HTTP或HTTPS）。 配置文件还包含日志内容过滤选项和受控实验信息。 通过对照实验，网站设计人员可以对所有网站访客的子集进行测试或设计更改。

更改其他 [!DNL txlogd.conf] 参数，如的IP地址 [!DNL data workbench server] 或 [!DNL Sensor]，则可以简单地将 [!DNL txlogd.conf] 和 [!DNL Sensor] 会自动选取更改。 在某些系统上，如果不停止Web服务器或发送器进程，您可能无法编辑或替换文件。

**打开和编辑txlogd.conf**

1. 浏览到 [!DNL Sensor] 安装目录并打开 [!DNL txlogd.conf] 文件。
1. 根据需要编辑文件。
1. 保存并关闭该文件。

   * 受控实验配置文件(由 [!DNL txlogd.conf] 文件)应位于web服务器上的目录中，该目录可供web内容开发人员访问或由内容管理系统控制。
   * ExpCookieURL参数中的值是用于测试网站的虚拟页面。 访问该页面的用户将获得新的跟踪ID。

有关使用的更多信息 [!DNL txlogd.conf]，请联系Adobe咨询服务。
