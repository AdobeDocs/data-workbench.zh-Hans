---
description: 通过设置警报、检查传感器的系统状态等检查发射器是否正在运行。
solution: Insight
title: 确认数据发射机正在运行
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 确认数据发射机正在运行{#confirming-that-the-data-transmitter-is-running}

通过设置警报、检查传感器的系统状态等检查发射器是否正在运行。

**推荐频率：** 每5-10分钟

* [检查发射器进程是否正在运行。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [在Insight Server中设置管理警报。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [检查传感器的系统状态。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 检查发射器进程 {#section-79806fa3b7034a8eaf571a66e24874d7}

验证发射器是否正在运行的一种方法是检查发射器进程是否在安装实例的 [!DNL Sensor] 每个Web服务器上 [!DNL Sensor] 运行。 发射器进程在Web服务器的进程列表中显示为“txlogd”。 您可以使用系统监视工具执行此检查。

## 在Data Workbench Server中设置管理警报 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

验证发射器是否正在运行的另一种方法是在中设置自动管理警报 [!DNL data workbench server]。 当已配置管理警报时，当其未从已配置且先前已连接的数据接收到数据时，该警报会生成电子邮件警报，该数据在文件的 [!DNL data workbench server] Alert Timeout(min)参数中指定的时 [!DNL Sensor] 间范围内 [!DNL Sensor][!DNL data workbench server’s][!DNL Administrative Alerts.cfg] 。 For more information about setting up administrative alerts, see the *Server Products Installation and Administration Guide*.

## 检查传感器的系统状态 {#section-de9d7e359242487a9fbead4ed65aebbc}

验证发射器是否正在运行的另一种方法是手动检查Data Workbench [!DNL Servers Manager] 中的。

**查看[!DNL Servers Manager]**

* 在Data Workbench中，右键单击工作区，单击，然 **[!UICONTROL Admin]**&#x200B;后在下方 [!DNL Manage]单击 **[!UICONTROL Servers]**。

如果某个图标为 [!DNL Sensor] 绿色，则发射器正在运行。

For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench[!DNL Sensor]Guide*.
