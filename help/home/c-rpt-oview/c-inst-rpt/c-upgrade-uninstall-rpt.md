---
description: 有关升级和卸载Report Server软件的信息。
solution: Analytics
title: 升级和卸载Report Server
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 升级和卸载Report Server{#upgrading-and-uninstalling-report-server}

有关升级和卸载Report Server软件的信息。

* [升级报告](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [卸载报告](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## 升级报告服务器 {#section-95fea4bddad74616a8aea450dcdb2282}

如果您要升级到 [!DNL Report Server] 5.4，则可以使用说明升级您的软 [!DNL Report Server] 件。 如果您使用的是 [!DNL Report Server] 3.6或更早版本，请与Adobe联系以获得升级帮助。

要升级 [!DNL Report Server] 5.4，请使用Data Workbench将升级文件复制到连接到的Data Workbench Server上 [!DNL Report Server] 。 执行此操作后， [!DNL Report] Server实例在连接到该服务器并加载配置文件时自动升级自己。

>[!NOTE]
>
>升级之 [!DNL Report Server]前，请确保正确升级了Data Workbench Server软件以及Data Workbench Server上运行的配置文件。 有关详细信息，请联系 Adobe 咨询服务部门。

要执行以下过程，您首先必须获得升级文件 [!DNL Report Server]。

**升级到[!DNL Report Server]5.4及更高版本**

1. 备份该目录下的所有文件并删 [!DNL E:\Portal] 除该目录下的所有文件和文件夹。
1. 将新内部版本的内容复制到中 [!DNL E:\Portal]。
1. 根据 [!DNL global.asa]上一 [!DNL email.asp]节中的说 [!DNL TopNavigation.xml] 明修改、修改和修改。

1. 从备份 [!DNL users.mdb] 中复制。

   >[!NOTE]
   >
   >如果以前没有生成输出为。png的报表，则需要进入单个报表文件夹并修改该文件夹以包 [!DNL reports.xml] 含png的报表格式。 否则，您可能会收到500错误。 您的原 [!DNL reports.xml] 始版本将类似于：

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   它需要修改为：

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. 在中， [!DNL report.cfg]包括png和save的输出格式。 以后，它应生成png格式的报告。

**升级到[!DNL Report Server]4.0**

1. 在Data Workbench计算机上，将Report Server升级文件复制到Data Workbench [!DNL Temp\Software] 安装目录中的文件夹。
1. 启动数据工作台并加载配置 [!DNL Configuration] 文件。
1. 单击缩 **[!UICONTROL Configure Connection to Servers]** 略图。
1. 在中， [!DNL Servers Manager]右键单击Data Workbench Server图标，然后单击 **[!UICONTROL Server Files]**。

1. 在“软件”文件夹中，打开该文 [!DNL Report Server] 件夹。
1. 右键单击对 **[!UICONTROL Temp]** 应的复选标 [!DNL ReportServer.exe] 记，然后 **[!UICONTROL Save to]** 选择> *&lt;**[!UICONTROL server name]**>*。

## 卸载Report Server {#section-96eb3281c45a45c0a7065deaa6845c25}

**卸载[!DNL Report Server]**

1. 取消注册 [!DNL Report Windows] 服务。

   1. 打开命令提示符，然后导航到Data Workbench Server(InsightServer64.exe)安装文件夹中的bin子目录。示例：[!DNL D:\Adobe\Report\bin]
   1. 在命令提示符下，执行以下命令以在Microsoft Windows下停止并取消注册它为服务： [!DNL visualreport /unregserver]

1. 删除Report Server安装目录。

