---
description: 报告门户使用名为global.asa的配置文件中的信息来初始化用户会话。
title: 编辑会话配置文件
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# 编辑会话配置文件{#edit-the-session-configuration-file}

报告门户使用名为global.asa的配置文件中的信息来初始化用户会话。

安装[!DNL Report Portal]时，必须按照指示编辑此文件。 [!DNL global.asa]文件驻留在\*PortalName*\PortalASP\ folder中。

>[!NOTE]
>
>请勿更改此配置文件中的任何其他参数。

1. 在运行IIS的计算机上，在文本编辑器（如记事本）中打开[!DNL global.asa]文件。
1. 可选。要让用户在不进行身份验证的情况下访问[!DNL Report Portal]，请将Session(&quot;In&quot;)参数值更改为true。 默认值为false，将验证所有尝试访问[!DNL Report Portal]的用户。
1. 如果[!DNL Report Portal]安装在C驱动器以外的驱动器上，请将Session(&quot;Drive&quot;)参数的值更改为正确的驱动器位置。
1. 对于Session(&quot;DBPath&quot;)参数，更改该值以反映数据库的路径，该路径包含验证[!DNL Report Portal]用户所需的信息。 不要包含驱动器号，但应确保包含尾斜线。

   示例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. 保存文件。
1. 要验证[!DNL Report Portal]文件是否已正确安装，并且可以通过其指定的虚拟目录访问它们，请在浏览器中打开以下页：

   http://*YourServerAddress*/*YourPortalName*

   示例：[!DNL http://localhost/VisualReportPortal]

   如果[!DNL Report Portal] ASP安装正确，则应当看到门户登录页。 如果未看到此页，请验证IIS上是否启用了ASP，并多次检查虚拟目录映射。
