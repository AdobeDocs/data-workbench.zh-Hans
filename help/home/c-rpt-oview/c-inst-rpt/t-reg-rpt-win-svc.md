---
description: 注册和运行报表服务器的步骤。
title: 将报表服务器注册为 Windows 服务
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 8%

---

# 将报表服务器注册为 Windows 服务{#registering-report-server-as-a-windows-service}

注册和运行报表服务器的步骤。

在执行此过程之前，请标识[!DNL Report Server]服务将运行的Windows帐户。 确保此帐户具有访问存储生成报告的位置的适当权限（即，请勿使用[!DNL Local System Account]）。

请按照以下过程开始[!DNL Report Server]。 首次开始[!DNL Report Server]时，它会自动注册为Windows服务。

首次启动 [!DNL Report Server] 时，它会自动连接到 Adobe 许可证服务器以注册您的数字证书。要成功完成注册过程，您执行以下步骤时必须将计算机连接到Internet。

1. 在Windows中，导航到安装[!DNL Report Server]的目录。

   示例：D:\Adobe\Report

1. 多次 — 单击&#x200B;**[!UICONTROL ReportServer.exe]**。
1. 要确认[!DNL Report Server]是否正确运行，请单击&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**。 此命令序列可能因您使用的Windows版本而异。
1. 在服务列表中，找到[!DNL Report Server]的条目，并确认其状态为“Started（启动）” ，其启动类型为“Automatic（自动）”。
1. 执行以下操作以指定执行[!DNL Report Server]的用户帐户：

   1. 多次 — 单击&#x200B;**[!UICONTROL Report Server]**&#x200B;打开[!DNL Properties]窗口。

   1. 选择&#x200B;**[!UICONTROL Log On]**&#x200B;选项卡。
   1. 选择&#x200B;**[!UICONTROL This account]**&#x200B;单选按钮。
   1. 键入或浏览帐户名。 此帐户必须具有访问存储生成报告的位置的权限。

      >[!NOTE]
      >
      >如果[!DNL Report Server]以Microsoft Excel（[!DNL .xls]或[!DNL .xlsx]）文件的形式分发报表，请确保帐户还具有运行Microsoft Excel的权限。

   1. 输入并确认帐户的密码。
   1. 单击 **[!UICONTROL OK]**。

1. 右键单击[!DNL Report Server]服务，然后选择&#x200B;**[!UICONTROL Restart]**&#x200B;以在您指定的帐户下重新启动该服务。
1. 要检查开始过程中[!DNL Report Server]是否出现任何错误，请单击&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**。 此命令序列可能因您使用的Windows版本而异。

   1. 在[!DNL Event Viewer]窗口的左窗格中，选择应用程序日志。
   1. 在右侧窗格中，在[!DNL Source]列中查找带有Adobe的事件。
   1. 如果从Adobe中找到错误，请按住多次键单击该错误以显示[!DNL Event Properties]窗口。 此窗口提供有关错误的详细信息。

      >[!NOTE]
      >
      >在[!DNL Report Server]服务开始后，文件[!DNL ReportServer.log]将创建在报表服务器[!DNL Trace]目录中。 此文件对于诊断[!DNL Report Server]问题也很有用。

您已完成[!DNL Report Server]的安装。 [!DNL Report Server] 设计为连续运行。如果重新启动计算机，[!DNL Report Server]将自动重新启动。 如果需要手动开始并停止[!DNL Report Server]，则可以使用Windows中的[!DNL Services]控制面板执行此操作。
