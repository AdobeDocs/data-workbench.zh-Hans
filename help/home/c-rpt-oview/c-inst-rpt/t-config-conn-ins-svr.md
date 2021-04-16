---
description: 在生成报表和警报之前，必须配置报表服务器以指定Insight服务器的地址并标识您希望其报告的用户档案。
title: 配置与 Insight Server 的连接
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 9%

---

# 配置与 Insight Server 的连接{#configuring-the-connection-to-the-insight-server}

在生成报表和警报之前，必须配置报表服务器以指定Insight服务器的地址并标识您希望其报告的用户档案。

>[!NOTE]
>
>在如下所述配置报表服务器之前，您无法成功运行报表服务器。 如果尝试使用随项目安装的未配置文件运行报表服务器，报表服务器会生成一串错误。

**配置报表服务器**

1. 在Windows资源管理器中，导航到安装Report Server的目录。
1. 在记事本中打开[!DNL ReportServer.cfg]文件，并根据需要修改文件。

   以下示例[!DNL Report Server.cfg]默认仅包含[!DNL Report Server.cfg]文件中包含的参数（并高亮显示所需的参数设置）。 如果通过代理服务器与Adobe License Server联系，则需要添加授权矢量及其参数。 有关详细说明，请参阅[Report Server.cfg参数](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06)。

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
