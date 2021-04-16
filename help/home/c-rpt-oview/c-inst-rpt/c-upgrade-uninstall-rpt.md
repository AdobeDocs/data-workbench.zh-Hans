---
description: 有关升级和卸载Report Server软件的信息。
title: 升级和卸载报表服务器
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# 升级和卸载报表服务器{#upgrading-and-uninstalling-report-server}

有关升级和卸载Report Server软件的信息。

* [升级报告](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [卸载报告](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## 升级报表服务器{#section-95fea4bddad74616a8aea450dcdb2282}

如果您要升级到[!DNL Report Server] 5.4，则可以使用说明升级您的[!DNL Report Server]软件。 如果您使用[!DNL Report Server] 3.6或更早版本，请与Adobe联系以获得升级帮助。

要升级[!DNL Report Server] 5.4，请使用Data Workbench将升级文件复制到[!DNL Report Server]所连接的Data Workbench Server。 执行此操作后，[!DNL Report]服务器实例在连接到该服务器并加载用户档案时自动进行自升级。

>[!NOTE]
>
>在升级[!DNL Report Server]之前，请确保已正确升级Data Workbench Server软件以及Data Workbench Server上运行的用户档案。 有关详细信息，请联系 Adobe 咨询服务部门。

要执行以下过程，您首先必须获取[!DNL Report Server]的升级文件。

**升级到 [!DNL Report Server] 5.4及更高版本**

1. 备份[!DNL E:\Portal]下的所有文件，并删除此目录中的所有文件和文件夹。
1. 将新内部版本的内容复制到[!DNL E:\Portal]中。
1. 按照上一节中的说明修改[!DNL global.asa]、[!DNL email.asp]和[!DNL TopNavigation.xml]。

1. 从备份中复制[!DNL users.mdb]。

   >[!NOTE]
   >
   >如果之前未生成输出为.png的报表，则需要进入单个报表文件夹并修改[!DNL reports.xml]以包含png的报表格式。 否则，可能会出现500错误。 原始[!DNL reports.xml]的外观如下所示：

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

1. 在[!DNL report.cfg]中，包含png和save的输出格式。 今后，它应生成png格式的报表。

**升级到 [!DNL Report Server] 4.0**

1. 在Data Workbench计算机上，将Report Server升级文件复制到Data Workbench安装目录的[!DNL Temp\Software]文件夹。
1. 开始Data Workbench并加载[!DNL Configuration]用户档案。
1. 单击&#x200B;**[!UICONTROL Configure Connection to Servers]**&#x200B;缩略图。
1. 在[!DNL Servers Manager]中，右键单击Data Workbench Server图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在“软件”文件夹中，打开[!DNL Report Server]文件夹。
1. 右键单击[!DNL ReportServer.exe]的&#x200B;**[!UICONTROL Temp]**&#x200B;复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 卸载报表服务器{#section-96eb3281c45a45c0a7065deaa6845c25}

**卸载[!DNL Report Server]**

1. 注销[!DNL Report Windows]服务。

   1. 打开命令提示符，然后导航到Data Workbench Server(InsightServer64.exe)安装文件夹中的bin子目录。 示例：[!DNL D:\Adobe\Report\bin]
   1. 在命令提示符下，执行以下命令以在Microsoft Windows下停止并注销它作为服务：[!DNL visualreport /unregserver]

1. 删除Report Server安装目录。
