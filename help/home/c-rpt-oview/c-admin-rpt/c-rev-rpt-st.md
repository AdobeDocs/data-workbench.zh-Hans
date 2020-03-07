---
description: 有关报告服务器状态和报告集状态的信息。
solution: Analytics
title: 审核报告状态
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 审核报告状态{#reviewing-report-status}

有关报告服务器状态和报告集状态的信息。

* [报告服务器状态](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [报告集状态](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## 报告服务器状态 {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**推荐频率：** 仅在必要时

[!DNL Report] 每两分钟向Data Workbench Server发送有关服务器状态的状态信 [!DNL Report] 息。 此信息可在接口的节 [!DNL Report Server Status] 点下查看 [!DNL Detailed Status] 。

**打开可视[!DNL Detailed Status]化**

1. 在Data Workbench中，右键单击工作区，然后单击 **[!UICONTROL Admin]** > **[!UICONTROL Servers]**。

1. 在界 [!DNL Servers] 面中，右键单击计算机所连接的Data Workbench Server的图 [!DNL Report] 标，然后单击 **[!UICONTROL Detailed Status.]**

1. 单击 **[!UICONTROL Report Server Status]**.

如果多个Data Workbench [!DNL Report] Server连接到该服务器，则“状态”矢量中的每个Data Workbench Server都 [!DNL Report Server] 会显示一个条目。 通过在文件的节点中的Status Interval（秒）参数中指定一个值，可以覆盖两分钟 [!DNL Reporting] 的间隔时 [!DNL ReportServer.cfg] 间。

有关文件的信 [!DNL ReportServer.cfg] 息，请参 [阅配置报告集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)。 有关配置的信息，请 [!DNL Report]参阅安 [装报告](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91)。

For more information about [!DNL Detailed Status], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

## 报告集状态 {#section-8569b94266b74a1f85d2a85106a2aaef}

**推荐频率：** 仅在必要时

[!DNL Report] 将每个报告集的状态信息传输到Data Workbench Server。 基本信息（例如，生成报表集时以及报表集的分发位置）以绿色文本显示在报表集上方的数据工作台中。 运行报告时， [!DNL Report] Server每两分钟输出一条消息，指明当前查询的完成百分比。 通过在文件的节点中的“完成消息间隔（秒）”参数中指定一个值，可以覆盖这两分 [!DNL Reporting] 钟的间 [!DNL ReportServer.cfg] 隔。

![](assets/report_status.png)

>[!NOTE]
>
>如果运行报告时出错，则该错误以该报告缩略图下方的红色文本表示。 您可以右键单击工作区以显示完整的错误消息。

