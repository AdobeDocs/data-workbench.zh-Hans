---
description: 注册和运行Report Server的步骤。
solution: Analytics
title: 将Report Server注册为Windows服务
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 将Report Server注册为Windows服务{#registering-report-server-as-a-windows-service}

注册和运行Report Server的步骤。

在执行此过程之前，请标识服务将运行 [!DNL Report Server] 的Windows帐户。 确保此帐户具有访问存储生成报告的位置的适当权限(即，请勿使用 [!DNL Local System Account])。

请按照以下步骤开始 [!DNL Report Server]。 首次启动 [!DNL Report Server] 时，它会自动注册为Windows服务。

首次启动 [!DNL Report Server] 时，它会自动连接到 Adobe 许可证服务器以注册您的数字证书。要成功完成注册过程，您必须在执行以下步骤时将计算机连接到Internet。

1. 在Windows中，导航到您安装的目录 [!DNL Report Server]。

   示例：D:\Adobe\Report

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. 要确认正 [!DNL Report Server] 确运行，请单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**。 此命令序列可能因您所使用的Windows版本而异。
1. 在服务列表中，找到相应的条目， [!DNL Report Server] 并确认其状态为“启动”，其启动类型为“自动”。
1. 执行以下操作以指定将执行的用户 [!DNL Report Server] 帐户：

   1. 双击以 **[!UICONTROL Report Server]** 打开窗 [!DNL Properties] 口。

   1. 选择选 **[!UICONTROL Log On]** 项卡。
   1. 选择单 **[!UICONTROL This account]** 选按钮。
   1. 键入或浏览帐户名称。 此帐户必须具有访问存储生成报告的位置的权限。

      >[!NOTE]
      >
      >如果 [!DNL Report Server] 以Microsoft Excel（或）文件 [!DNL .xls] 的形式分 [!DNL .xlsx]发报表，请确保帐户还具有运行Microsoft Excel的权限。

   1. 输入并确认帐户的密码。
   1. 单击 **[!UICONTROL OK]**.

1. 右键单击该服 [!DNL Report Server] 务，然后选择以 **[!UICONTROL Restart]** 您指定的帐户重新启动该服务。
1. 要检查在启 [!DNL Report Server] 动过程中是否遇到任何错误，请单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**。 此命令序列可能因您所使用的Windows版本而异。

   1. 在窗口的左窗格中，选 [!DNL Event Viewer] 择“应用程序”日志。
   1. 在右侧窗格中，查找列中与Adobe一起发生的 [!DNL Source] 活动。
   1. 如果您从Adobe找到错误，请双击该错误以显示该窗 [!DNL Event Properties] 口。 此窗口提供有关错误的详细信息。

      >[!NOTE]
      >
      >服务启 [!DNL Report Server] 动后，将在Report Server目 [!DNL ReportServer.log] 录中创建该 [!DNL Trace] 文件。 此文件还可用于排除问题 [!DNL Report Server]。

您已完成安装 [!DNL Report Server]。 [!DNL Report Server] 设计为连续运行。 如果重新启动计算机，将自动 [!DNL Report Server] 重新启动。 如果需要手动启动和停止， [!DNL Report Server] 则可以使用Windows中的控 [!DNL Services] 制面板执行此操作。
