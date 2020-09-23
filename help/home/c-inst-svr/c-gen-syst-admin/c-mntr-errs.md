---
description: 要尽快检测系统和应用程序错误并在它们导致严重问题或中断之前解决它们，您应定期监控事件日志。
solution: Analytics
title: 监控错误事件
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---


# 监控错误事件{#monitoring-events-for-errors}

要尽快检测系统和应用程序错误并在它们导致严重问题或中断之前解决它们，您应定期监控事件日志。

**推荐频率：** 每5-10分钟

要监控Adobe服务器软件产品，可以设置自动化管理工具来监控事件日志中源“Adobe”错误，然后提醒相应人员可能需要干预的问题。

在Windows中，应用程序错误消息将输出到Windows中的应用程序事件日志，您可以使用Windows事件查看器访问该日志。 在Unix中，应用程序错误消息使用LOG_DAEMON工具输出到Unix系统日志。

**打开Windows事件查看器**

* 单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

