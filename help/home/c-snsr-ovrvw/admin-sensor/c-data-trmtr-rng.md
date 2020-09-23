---
description: 通过设置警报、检查传感器的系统状态等检查发射器是否正在运行。
solution: Analytics
title: 确认数据发送器正在运行
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---


# 确认数据发送器正在运行{#confirming-that-the-data-transmitter-is-running}

通过设置警报、检查传感器的系统状态等检查发射器是否正在运行。

**推荐频率：** 每5-10分钟

* [检查发射器进程是否正在运行。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [在Insight Server中设置管理警报。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [检查传感器的系统状态。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 检查发射器进程 {#section-79806fa3b7034a8eaf571a66e24874d7}

验证发射器是否正在运行的一种方法是检查在安装了实例 [!DNL Sensor] 的每个Web服务器上是否正在运行 [!DNL Sensor] 发射器进程。 发送器进程在Web服务器的进程列表中显示为“txlogd”。 您可以使用系统监视工具执行此检查。

## 在Data Workbench服务器中设置管理警报 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

验证发射器是否正在运行的另一种方法是在中设置自动管理警报 [!DNL data workbench server]。 当管理警报已配置时，当 [!DNL data workbench server] 在文件中的警报超时(min)参数中指定的时间范围内未收到已配置和先前连接的数据时， [!DNL Sensor] 将生成电子邮件 [!DNL Sensor][!DNL data workbench server’s][!DNL Administrative Alerts.cfg] 警报。 For more information about setting up administrative alerts, see the *Server Products Installation and Administration Guide*.

## 检查传感器的系统状态 {#section-de9d7e359242487a9fbead4ed65aebbc}

验证发射器是否正在运行的另一种方法是手动检查 [!DNL Servers Manager] Data Workbench。

**视图[!DNL Servers Manager]**

* 在Data Workbench中，右键单击工作区，单 **[!UICONTROL Admin]**&#x200B;击，然后在 [!DNL Manage]下单击 **[!UICONTROL Servers]**。

如果某个图标为 [!DNL Sensor] 绿色，则发射器正在运行。

For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench[!DNL Sensor]Guide*.
