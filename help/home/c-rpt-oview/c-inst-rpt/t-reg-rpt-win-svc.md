---
description: 注册和运行报表服务器的步骤。
title: 将报表服务器注册为 Windows 服务
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 8%

---

# 将报表服务器注册为 Windows 服务{#registering-report-server-as-a-windows-service}

{{eol}}

注册和运行报表服务器的步骤。

在执行此过程之前，请确定 [!DNL Report Server] 服务将运行。 确保此帐户具有访问存储生成报表的位置的适当权限(即，不要使用 [!DNL Local System Account])。

请使用以下过程开始 [!DNL Report Server]. 开始时 [!DNL Report Server] 它首次自动将其注册为Windows服务。

首次启动 [!DNL Report Server] 时，它会自动连接到 Adobe 许可证服务器以注册您的数字证书。要成功完成注册过程，您必须在执行以下步骤时将计算机连接到Internet。

1. 在Windows中，导航到安装的目录 [!DNL Report Server].

   示例：D:\Adobe\Report

1. 双击 **[!UICONTROL ReportServer.exe]**.
1. 确认 [!DNL Report Server] 运行正确，单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. 此命令序列可能因您使用的Windows版本而异。
1. 在服务列表中，找到 [!DNL Report Server] 并确认其状态为“已启动”且其启动类型为“自动”。
1. 请执行以下操作，以指定用户帐户 [!DNL Report Server] 将执行：

   1. 双击 **[!UICONTROL Report Server]** 打开 [!DNL Properties] 窗口。

   1. 选择 **[!UICONTROL Log On]** 选项卡。
   1. 选择 **[!UICONTROL This account]** 按钮。
   1. 键入或浏览帐户名称。 此帐户必须具有访问存储生成报表的位置的权限。

      >[!NOTE]
      >
      >如果 [!DNL Report Server] 以Microsoft Excel格式分发报表( [!DNL .xls] 或 [!DNL .xlsx])文件，请确保帐户还具有运行Microsoft Excel的权限。

   1. 输入并确认帐户的密码。
   1. 单击 **[!UICONTROL OK]**。

1. 右键单击 [!DNL Report Server] 服务和选择 **[!UICONTROL Restart]** 要在您指定的帐户下重新启动服务，请执行以下操作：
1. 检查是否 [!DNL Report Server] 在启动过程中遇到任何错误，请单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. 此命令序列可能因您使用的Windows版本而异。

   1. 在 [!DNL Event Viewer] 窗口，选择“应用程序”日志。
   1. 在右侧窗格中，查找在 [!DNL Source] 列。
   1. 如果从Adobe中发现错误，请双击该错误以显示 [!DNL Event Properties] 窗口。 此窗口提供有关错误的详细信息。

      >[!NOTE]
      >
      >在 [!DNL Report Server] 服务启动，文件 [!DNL ReportServer.log] 在报表服务器中创建 [!DNL Trace] 目录访问Advertising Cloud的帮助。 此文件还可用于解决 [!DNL Report Server].

您已完成 [!DNL Report Server]. [!DNL Report Server] 设计为连续运行。 如果重新启动计算机， [!DNL Report Server] 自动重新启动。 如果需要启动和停止 [!DNL Report Server] 手动操作时，您可以使用 [!DNL Services] 控制面板。
