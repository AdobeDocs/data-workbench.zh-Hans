---
description: 有关升级和卸载报表服务器软件的信息。
title: 升级和卸载报表服务器
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# 升级和卸载报表服务器{#upgrading-and-uninstalling-report-server}

{{eol}}

有关升级和卸载报表服务器软件的信息。

* [升级报告](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [卸载报表](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## 升级报表服务器 {#section-95fea4bddad74616a8aea450dcdb2282}

如果您要升级到 [!DNL Report Server] 5.4，您可以使用相关说明升级 [!DNL Report Server] 软件。 如果您使用 [!DNL Report Server] 3.6或更早版本，请联系Adobe以获取有关升级的帮助。

升级 [!DNL Report Server] 5.4，使用Data Workbench将升级文件复制到其 [!DNL Report Server] 连接。 这样做之后， [!DNL Report] 服务器实例在连接到该服务器并加载配置文件时会自动升级自身。

>[!NOTE]
>
>升级前 [!DNL Report Server]，请确保已正确升级Data Workbench Server软件以及Data Workbench Server上运行的配置文件。 有关详细信息，请联系 Adobe 咨询服务部门。

要执行以下过程，您必须首先获取 [!DNL Report Server].

**升级到 [!DNL Report Server] 5.4及更高版本**

1. 备份下的所有文件 [!DNL E:\Portal] 并删除此目录中的所有文件和文件夹。
1. 将新内部版本的内容复制到 [!DNL E:\Portal].
1. 修改 [!DNL global.asa], [!DNL email.asp]和 [!DNL TopNavigation.xml] 按照上一节的说明执行。

1. 复制 [!DNL users.mdb] 你的后备。

   >[!NOTE]
   >
   >如果您之前未生成输出为.png的报表，则需要转到单个报表文件夹并修改 [!DNL reports.xml] 以包含png的报表格式。 否则，您可能会收到500错误。 您的原始 [!DNL reports.xml] 会如下所示：

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

   需要将其修改为：

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

1. 在 [!DNL report.cfg]，包括png和save的输出格式。 今后，它应生成png格式的报表。

**升级到 [!DNL Report Server] 4.0**

1. 在Data Workbench计算机上，将报表服务器升级文件复制到 [!DNL Temp\Software] 文件夹。
1. 启动Data Workbench并加载 [!DNL Configuration] 配置文件。
1. 单击 **[!UICONTROL Configure Connection to Servers]** 缩略图。
1. 在 [!DNL Servers Manager]，右键单击data workbench server图标，然后单击 **[!UICONTROL Server Files]**.

1. 在Software文件夹中，打开 [!DNL Report Server] 文件夹。
1. 右键单击 **[!UICONTROL Temp]** 为 [!DNL ReportServer.exe] 选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 卸载报表服务器 {#section-96eb3281c45a45c0a7065deaa6845c25}

**卸载[!DNL Report Server]**

1. 取消注册 [!DNL Report Windows] 服务。

   1. 打开命令提示符，然后导航到Data Workbench Server(InsightServer64.exe)安装文件夹中的bin子目录。 示例：[!DNL D:\Adobe\Report\bin]
   1. 在命令提示符下，执行以下命令以在Microsoft Windows下停止并取消注册为服务： [!DNL visualreport /unregserver]

1. 删除Report Server安装目录。
