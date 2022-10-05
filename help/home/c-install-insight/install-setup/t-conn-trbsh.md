---
description: 如果 Insight 无法使用指定的设置连接到 Insight Server，则会在服务器管理器中显示一个红色的节点。
title: 连接故障排除
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 56%

---

# 连接故障排除{#connection-troubleshooting}

{{eol}}

如果 Insight 无法使用指定的设置连接到 Insight Server，则会在服务器管理器中显示一个红色的节点。

例如，如果您未正确配置连接，或者您没有查看 [!DNL Insight Server’s] 状态。

**确定Insight无法建立连接的原因**

1. 右键单击红色的服务器节点，然后单击 **[!UICONTROL Detailed Status]**.
1. 在 [!DNL Detailed Status] 界面，单击 **[!UICONTROL Network Connections]** 并展开编号项目。 的 [!DNL Status] 参数提供有关Insight无法建立连接的原因的信息：

   * 状态代码为 500s 表示配置错误。
   * 状态代码为 403 通常表示您没有权限查看服务器的状态。

您可以在 [!DNL insight.log] 文件中查看其他状态信息。此日志文件位于 [!DNL Trace] 文件夹。 若要查看该文件，请在文本编辑器（如记事本）中打开。

如果您在了解 [!DNL insight.log] 文件中信息时需要帮助，请首先与您的系统管理员联系。如果您需要进一步的帮助，请联系Adobe客户关怀团队。
