---
description: 在生成报告和警报之前，必须配置Report Server，以指定Insight Server的地址并标识要报告的配置文件。
solution: Analytics
title: 配置与Insight Server的连接
topic: Data workbench
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuring the Connection to the Insight Server{#configuring-the-connection-to-the-insight-server}

在生成报告和警报之前，必须配置Report Server，以指定Insight Server的地址并标识要报告的配置文件。

>[!NOTE]
>
>在如下所述配置报表服务器之前，您无法成功运行报表服务器。 如果尝试使用随程序安装的未配置文件运行报告服务器，报告服务器会生成一串错误。

**配置报告服务器**

1. 使用Windows资源管理器，导航到您安装Report Server的目录。
1. 在记事 [!DNL ReportServer.cfg] 本中打开文件，并根据需要修改文件。

   以下示例 [!DNL Report Server.cfg] 仅包含文件中默认包含的 [!DNL Report Server.cfg] 参数（并高亮显示所需的参数设置）。 如果通过代理服务器与Adobe许可证服务器联系，则需要添加许可矢量及其参数。 有关 [详细说明，请参阅Report Server](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) .cfg参数。

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. 保存并关闭该文件。
