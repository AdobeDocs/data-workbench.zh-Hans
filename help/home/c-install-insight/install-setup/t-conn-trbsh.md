---
description: 如果 Insight 无法使用指定的设置连接到 Insight Server，则会在服务器管理器中显示一个红色的节点。
title: 连接疑难排解
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 连接疑难排解{#connection-troubleshooting}

如果 Insight 无法使用指定的设置连接到 Insight Server，则会在服务器管理器中显示一个红色的节点。

This might occur, for example, if you configure the connection incorrectly or you do not have permission to view the [!DNL Insight Server’s] status.

**确定Insight无法建立连接的原因**

1. Right-click the red server node and click **[!UICONTROL Detailed Status]**.
1. 在界面 [!DNL Detailed Status] 中，单击并 **[!UICONTROL Network Connections]** 展开编号项目。 The [!DNL Status] parameter provides information about why Insight is not able to establish a connection:

   * 状态代码为 500s 表示配置错误。
   * 状态代码为 403 通常表示您没有权限查看服务器的状态。

您可以在 [!DNL insight.log] 文件中查看其他状态信息。This log file is located in the [!DNL Trace] folder in the directory where you installed Insight. 若要查看该文件，请在文本编辑器（如记事本）中打开。

如果您在了解 [!DNL insight.log] 文件中信息时需要帮助，请首先与您的系统管理员联系。如果您需要进一步的帮助，请与Adobe客户关怀联系。
