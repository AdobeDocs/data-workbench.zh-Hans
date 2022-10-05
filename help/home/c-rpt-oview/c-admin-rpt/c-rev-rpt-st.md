---
description: 有关报表服务器状态和报表集状态的信息。
title: 审核报表状态
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# 审核报表状态{#reviewing-report-status}

{{eol}}

有关报表服务器状态和报表集状态的信息。

* [报表服务器状态](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [报表集状态](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## 报表服务器状态 {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**推荐频率：** 仅在必要时

[!DNL Report] 每两分钟向data workbench server发送一次有关 [!DNL Report] 服务器。 此信息可在 [!DNL Report Server Status] 节点 [!DNL Detailed Status] 界面。

**要打开 [!DNL Detailed Status] 可视化**

1. 在Data Workbench中，右键单击工作区，然后单击 **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. 在 [!DNL Servers] 界面中，右键单击 [!DNL Report] 计算机连接到并单击 **[!UICONTROL Detailed Status.]**

1. 单击 **[!UICONTROL Report Server Status]**。

如果多个 [!DNL Report] 连接到data workbench服务器后，将为每个 [!DNL Report Server] 中。 两分钟的间隔可通过在 [!DNL Reporting] 节点 [!DNL ReportServer.cfg] 文件。

有关 [!DNL ReportServer.cfg] 文件，请参阅 [配置报表集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). 有关配置的信息 [!DNL Report]，请参阅 [安装报表](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

有关 [!DNL Detailed Status]，请参阅 *Data Workbench用户指南*.

## 报表集状态 {#section-8569b94266b74a1f85d2a85106a2aaef}

**推荐频率：** 仅在必要时

[!DNL Report] 将每个报告集的状态信息发送到Data Workbench服务器。 基本信息（例如，在生成报表集并在其中分发报表集时）以绿色文本显示在报表集上方的Data Workbench中。 运行报表时， [!DNL Report] 服务器每两分钟输出一条消息，指示当前查询的完成百分比。 通过在 [!DNL Reporting] 节点 [!DNL ReportServer.cfg] 文件。

![](assets/report_status.png)

>[!NOTE]
>
>如果运行报表时出错，则该错误会以该报表缩略图下方的红色文本表示。 您可以右键单击工作区以显示完整的错误消息。
