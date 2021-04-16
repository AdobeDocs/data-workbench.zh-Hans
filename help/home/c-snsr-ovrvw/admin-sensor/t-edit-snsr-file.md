---
description: 传感器配置文件txlogd.conf包含传感器用来与Data Workbench Server建立连接的参数。
title: 编辑传感器 txlogd.conf 文件
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 7%

---

# 编辑传感器 txlogd.conf 文件{#editing-the-sensor-txlogd-conf-file}

传感器配置文件txlogd.conf包含传感器用来与Data Workbench Server建立连接的参数。

这些参数包括服务器的地址、端口号和通信协议（HTTP或HTTPS）。 配置文件还包含日志内容过滤选项和受控实验信息。 受控实验使站点设计人员能够对所有站点访客的子集进行测试或设计更改。

当更改其他[!DNL txlogd.conf]参数（如[!DNL data workbench server]的IP地址或[!DNL Sensor]的名称）时，您可能只需将[!DNL txlogd.conf]替换为更新版本，而[!DNL Sensor]将自动接收更改。 在某些系统上，如果不停止Web服务器或发送器进程，您可能无法编辑或替换文件。

**打开和编辑txlogd.conf**

1. 浏览至[!DNL Sensor]安装目录，并在文本编辑器中打开[!DNL txlogd.conf]文件。
1. 根据需要编辑文件。
1. 保存并关闭该文件。

   * 受控实验配置文件的位置（由[!DNL txlogd.conf]文件中的ExpFile参数定义）应位于Web服务器上的一个目录中，Web内容开发者可访问该目录或由内容管理系统控制。
   * ExpCookieURL参数中的值是用于测试网站的虚拟页。 访问该页面的用户将获得新的跟踪ID。

有关使用[!DNL txlogd.conf]的详细信息，请与Adobe咨询服务部门联系。
