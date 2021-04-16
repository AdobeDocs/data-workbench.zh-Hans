---
description: 有关报表服务器状态和报表集状态的信息。
title: 审核报表状态
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# 审核报表状态{#reviewing-report-status}

有关报表服务器状态和报表集状态的信息。

* [报表服务器状态](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [报表集状态](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## 报表服务器状态{#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**推荐频率：仅** 在必要时

[!DNL Report] 每两分钟向data workbench server发送有关服务器状态的状态 [!DNL Report] 信息。此信息可在[!DNL Detailed Status]接口的[!DNL Report Server Status]节点下查看。

**打开可视 [!DNL Detailed Status] 化**

1. 在Data Workbench中，右键单击工作区，然后单击&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Servers]**。

1. 在[!DNL Servers]接口中，右键单击[!DNL Report]计算机所连接的Data Workbench Server的图标，然后单击&#x200B;**[!UICONTROL Detailed Status.]**

1. 单击 **[!UICONTROL Report Server Status]**。

如果多个[!DNL Report]连接到Data Workbench Server，则“状态”矢量中将显示每个[!DNL Report Server]的条目。 通过在[!DNL ReportServer.cfg]文件的[!DNL Reporting]节点中的Status Interval（秒）参数中指定值，可以覆盖两分钟间隔。

有关[!DNL ReportServer.cfg]文件的信息，请参阅[配置报表集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)。 有关配置[!DNL Report]的信息，请参阅[安装报告](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91)。

有关[!DNL Detailed Status]的详细信息，请参阅&#x200B;*《Data Workbench用户指南》*&#x200B;的“管理界面”一章。

## 报表集状态{#section-8569b94266b74a1f85d2a85106a2aaef}

**推荐频率：仅** 在必要时

[!DNL Report] 向Data Workbench服务器发送每个报告集的状态信息。基本信息（例如生成报表集的时间和分发报表集的位置）将以绿色文本显示在报表集上方的Data Workbench中。 运行报告时，[!DNL Report]服务器每两分钟输出一条消息，指示当前查询的完成百分比。 通过在[!DNL ReportServer.cfg]文件的[!DNL Reporting]节点中的“完成消息间隔（秒）”参数中指定值，可以覆盖此两分钟间隔。

![](assets/report_status.png)

>[!NOTE]
>
>如果运行报表时出错，则该错误以该报表缩略图下方的红色文本表示。 您可以右键单击工作区以显示完整的错误消息。
