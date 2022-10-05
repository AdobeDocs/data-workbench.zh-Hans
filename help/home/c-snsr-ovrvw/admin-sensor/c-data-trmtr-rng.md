---
description: 通过设置警报、检查传感器的系统状态等检查发送器是否正在运行。
title: 确认数据发送器正在运行
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# 确认数据发送器正在运行{#confirming-that-the-data-transmitter-is-running}

{{eol}}

通过设置警报、检查传感器的系统状态等检查发送器是否正在运行。

**推荐频率：** 每5-10分钟

* [检查发送器进程是否正在运行。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [在Insight Server中设置管理警报。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [检查传感器的系统状态。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 检查发送器进程 {#section-79806fa3b7034a8eaf571a66e24874d7}

验证发送器是否正在运行的一种方法是检查 [!DNL Sensor] 发送器进程在每个web服务器上运行，其中 [!DNL Sensor] 安装实例。 发送器进程在Web服务器的进程列表中显示为“txlogd”。 您可以使用系统监控工具执行此检查。

## 在Data Workbench服务器中设置管理警报 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

验证发送器是否正在运行的另一种方法是，在 [!DNL data workbench server]. 配置管理警报后， [!DNL data workbench server] 当未收到来自已配置且先前已连接的 [!DNL Sensor] 在 [!DNL Sensor] 中的警报超时（分钟）参数 [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] 文件。 有关设置管理警报的更多信息，请参阅 *《服务器产品安装和管理指南》*.

## 检查传感器的系统状态 {#section-de9d7e359242487a9fbead4ed65aebbc}

而验证发射器是否正在运行的另一种方法是手动检查 [!DNL Servers Manager] Data Workbench。

**查看[!DNL Servers Manager]**

* 在Data Workbench中，右键单击工作区，然后单击 **[!UICONTROL Admin]**，然后在下 [!DNL Manage]，单击 **[!UICONTROL Servers]**.

如果 [!DNL Sensor] 绿色，发送器正在运行。

有关 [!DNL Servers Manager]，请参阅 *Data Workbench [!DNL Sensor] 指南*.
