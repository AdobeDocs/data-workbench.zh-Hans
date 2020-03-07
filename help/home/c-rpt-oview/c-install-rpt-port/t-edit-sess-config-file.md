---
description: 报告门户使用名为global.asa的配置文件中的信息来初始化用户会话。
solution: Analytics
title: 编辑会话配置文件
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 编辑会话配置文件{#edit-the-session-configuration-file}

报告门户使用名为global.asa的配置文件中的信息来初始化用户会话。

安装时， [!DNL Report Portal]必须按照指示编辑此文件。 文 [!DNL global.asa] 件位于\*PortalName*\PortalASP\ folder中。

>[!NOTE]
>
>请勿更改此配置文件中的任何其他参数。

1. 在运行IIS的计算机上，在文本编辑 [!DNL global.asa] 器（如记事本）中打开文件。
1. 可选。要让用户在不进 [!DNL Report Portal] 行身份验证的情况下访问，请将Session(&quot;In&quot;)参数值更改为true。 默认值为false，它将验证尝试访问的所有用户 [!DNL Report Portal]。
1. 如果您 [!DNL Report Portal] 安装在C驱动器以外的驱动器上，请将Session(&quot;Drive&quot;)参数的值更改为正确的驱动器位置。
1. 对于Session(&quot;DBPath&quot;)参数，更改值以反映数据库路径，该路径包含用户身份验证所需的信 [!DNL Report Portal] 息。 不要包括驱动器盘符，但应确保包含尾随斜杠。

   示例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. 保存文件。
1. 要验证文件是 [!DNL Report Portal] 否已正确安装，并且可以通过文件的指定虚拟目录访问这些文件，请在浏览器中打开以下页面：

   http://*YourServerAddress*/*YourPortalName*

   示例：[!DNL http://localhost/VisualReportPortal]

   如果 [!DNL Report Portal] ASP安装正确，您应当看到门户登录页。 如果看不到此页，请验证IIS上是否启用了ASP，并仔细检查虚拟目录映射。

