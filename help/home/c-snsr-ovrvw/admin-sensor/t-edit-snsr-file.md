---
description: 传感器配置文件txlogd.conf包含传感器用来与Data Workbench Server建立连接的参数。
solution: Insight
title: 编辑传感器txlogd.conf文件
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# 编辑传感器txlogd.conf文件{#editing-the-sensor-txlogd-conf-file}

传感器配置文件txlogd.conf包含传感器用来与Data Workbench Server建立连接的参数。

这些参数包括服务器的地址、端口号和通信协议（HTTP或HTTPS）。 配置文件还包含日志内容过滤选项和受控实验信息。 受控实验使站点设计人员能够对所有站点访客的子集进行测试内容或设计更改。

当更改其 [!DNL txlogd.conf] 他参数（如的IP地址或名称）时，您可能只需用更 [!DNL data workbench server] 新后的版本替换， [!DNL Sensor][!DNL txlogd.conf][!DNL Sensor] 即可自动获取更改。 在某些系统上，如果不停止Web服务器或发射器进程，您可能无法编辑或替换文件。

**打开和编辑txlogd.conf**

1. 浏览到安 [!DNL Sensor] 装目录，并在文本编 [!DNL txlogd.conf] 辑器中打开文件。
1. 根据需要编辑文件。
1. 保存并关闭该文件。

   * 受控实验配置文件的位置（由文件中的ExpFile参数定义）应位于Web服务器上的一个目录中，Web内容开发人员可访问该目录或由内容管理系统控制该目录。 [!DNL txlogd.conf]
   * ExpCookieURL参数中的值是用于测试网站的虚拟页面。 访问该页面的用户将获得新的跟踪ID。

有关使用的更多信息， [!DNL txlogd.conf]请与Adobe咨询服务部门联系。
