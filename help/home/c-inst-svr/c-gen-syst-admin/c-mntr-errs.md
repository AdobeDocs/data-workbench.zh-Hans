---
description: 要尽快检测系统和应用程序错误并在它们导致重大问题或中断之前解决它们，您应定期监控事件日志。
title: 监控错误事件
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---

# 监控错误事件{#monitoring-events-for-errors}

要尽快检测系统和应用程序错误并在它们导致重大问题或中断之前解决它们，您应定期监控事件日志。

**推荐频率：** 每5-10分钟

要监控Adobe服务器软件产品，可以设置自动管理工具来监控事件日志中源“Adobe”的错误，然后提醒相应人员注意可能需要干预的问题。

在Windows中，应用程序错误消息会输出到Windows中的应用程序事件日志，您可以使用Windows事件查看器访问该日志。 在Unix中，使用LOG_DAEMON工具将应用程序错误消息输出到Unix系统日志。

**打开Windows事件查看器**

* 单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
