---
description: 按照以下步骤，从安装的 Insight v5.5x 更新至 Data Workbench v6.1。
solution: Analytics
title: 从 Data Workbench 5.5 升级至 6.1
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 从 Data Workbench 5.5 升级至 6.1{#data-workbench-to-upgrade}

按照以下步骤，从安装的 Insight v5.5x 更新至 Data Workbench v6.1。

**步骤 1**：[服务器升级](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**步骤 2**：[Report Server 升级](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**步骤 3**：[客户端升级](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>升级服务器、报表服务器和客户端组件的目的是为了在 64 位 Windows 操作系统上运行。

## 服务器升级 {#section-08bd6fe3da8740fcb19688e8cac6f223}

Follow these steps to update the **[!UICONTROL Server v6.1]** components:

1. Using the **[!UICONTROL Software and Docs]** profile, open the **[!UICONTROL Start Here]** workspace and download all needed server packages to a local folder.

   * Download **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip folders and extract all files.

      The **[!UICONTROL Server]** package includes **[!UICONTROL Lookup]** and **[!UICONTROL Profile]** folders with the **[!UICONTROL Base]** and **[!UICONTROL Transform]** lookup files to add and replace to update the server.

   * Download new **[!UICONTROL Profiles]** folders.
   * Download updated **[!UICONTROL Lookup]** folders.
   * 下载 **[!UICONTROL Report Server]** \包 **[!UICONTROL v6.1]** 。
   * Download additional **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]**, and **[!UICONTROL Dashboard]** files as needed for your system.

1. Stop the **[!UICONTROL Adobe Insight Server]** service.

   ![](assets/install_server_download1.png)

1. From the downloaded **[!UICONTROL Server]** package:

   1. Replace the [!DNL Server\Bin] folder to update the [!DNL InsightServer64.exe] and supporting files.

   1. Replace the [!DNL Server\Profiles] folder. 您可以覆盖所有文件。
   1. Update the [!DNL Server\Lookups] folder. 您将需要将新下载的文件添加到文件夹中已存在的自定义文件中。
   1. Replace the [!DNL Server\Software] folder to update [!DNL Insight.exe] and [!DNL ReportServer.exe]

   1. Update the [!DNL Server\Scripts] folder to update [!DNL TnTSend.exe].

1. 如果采用 **[!UICONTROL DeviceAtlas]**，则将需要[更新捆绑包](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html)（位于 [!DNL Server\Lookups] 文件夹）。
1. 设置 [!DNL Directories] 中的 [!DNL Profile.cfg]，以确保矢量已更新，可以反映每个配置文件的项目数量。

   For example, to enable the **[!UICONTROL Predictive Analytics]** profile you will need to update this setting.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. 配置并保存 [!DNL PAServer.cfg] 文件，以升级“预测分析”功能。

   如果您需要将“预测分析”作业提交至服务器，则将需要配置 [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] 文件以便管理服务器端聚类提交。

   自定义配置文件应该从“预测分析”配置文件继承设置，从而允许您根据站点实施配置并保存 [!DNL PAServer.cfg]。

1. 定义 **[!UICONTROL Log Source ID]**.

   添加 **[!UICONTROL Recording of Rows per Log Source]** 了唯一名 **[!UICONTROL v6.04]** 称的自定义配置文件，并在 [!DNL Log Processing.cfg] 该文件中进行了定义 **[!UICONTROL Log Source ID]**。

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   如果没有定义“日志源 ID”，则将收到以下错误：

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. 由于 [!DNL EventMessages.dll] 已进行更新，因此您必须在聚类中取消注册 **[!UICONTROL Adobe Insight Server]**，然后再对其重新注册。

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Start the **[!UICONTROL Adobe Insight Server]** service across the cluster.

服务器安装现已完成。

## Report Server 升级 {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>升级到之 **[!UICONTROL Report Server v6.1]**&#x200B;前，必须先升级到 **[!UICONTROL Server v6.1]**。

1. 使用配 **[!UICONTROL Software and Docs]** 置文件，从包 **[!UICONTROL v6.1]** 下载 **[!UICONTROL Report Server]** 到本地文件夹。
1. 复制下载的包中的 **[!UICONTROL Report Server 6.1]** 并替换配置文件包。

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the [!DNL install] folder is a backup file used for localization, and must be present in the [!DNL install] directory. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up.

1. （可选）修改报表服务器配置文件，以支持双字节字符。

   Data Workbench当前支持英语(-en-us)和中文(-zh-cn)。 需要设置字体才能支持单字节和双字节字符：

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Windows 操作系统必须也安装了列出的这些字体。

1. 配置 [!DNL Report Server v6.1].

   1. Stop the **[!UICONTROL Adobe Insight Report Server]** service.
   1. 以“管理员”身份启动命令提示符。
   1. Navigate to the Report Server [!DNL install] folder.
   1. 使用以下命令删除 Report Server 服务。

      ```
      ReportServer.exe /unregserver
      ```

1. 根据语言设置启动服务：

   ```
   ReportServer.exe -RegServer -Locale -en-us (English) 
   ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
   ```

1. 要验证Report Server是否使用正确的设置运行，请打开并 **[!UICONTROL Windows Service Manager]** 右键单击 **[!UICONTROL Adobe Insight Report Server - Properties]**。 可执行文件的路径将显示更新后的命令行设置。

报表服务器安装现已完成。

## 客户端升级 {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Before upgrading to **[!UICONTROL Client v6.1]**, the administrator must first upgrade to **[!UICONTROL Server v6.1.]**

1. 启动 [!DNL Insight.exe]，但是不要连接任何配置文件。
1. 编辑 [!DNL Insight.cfg] 文件以便不自动更新软件。

   ```
   Update Software = bool: false
   ```

1. 连接到 **[!UICONTROL Software and Docs]** 配置文件(softdocs)。
1. 下载 [!DNL Software\Insight Client\v6.10].
1. （可选）修改 [!DNL insight.cfg] 以支持双字节字符。

   Data Workbench 目前支持英语和简体中文。选择用于支持这两种语言的字体：

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. 退出客户端。
1. 将下载的 **v6.1** 客户端包中的文件复制到 [!DNL Install] 文件夹中。

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the install folder is a backup file used for localization, and must be present in the install directory. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up.
   >
   >例如，要启动简体中文版，请创建一个用于传入命令行设置的的快捷方式。
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >如果您要以英语启动（默认），则不需要更改命令行。

1. 启动英语版 [!DNL Insight.exe] 或您为其他语言创建的快捷方式。
1. 连接到您的配置文件并允许客户端与服务器同步。
1. （可选）要使用 IME，请对 [!DNL Insight.cfg] 文件进行以下更改：

   ```
   Localized IME = bool: true
   ```

   输入法编辑器 (IME) 允许您输入国际字符。

1. （可选）编辑 [!DNL Insight.cfg] 文件以自动更新软件：

   ```
   Update Software = bool: true
   ```

   请参阅有关实施 IME 的说明。
1. Restart again after the profile synchronization to employ the most recent [!DNL .zbin] file.

客户端安装现已完成。
