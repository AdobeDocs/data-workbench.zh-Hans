---
description: ExpCookieURL参数可用于测试受控实验是否正常工作。
solution: Analytics
title: 修改 ExpCookieURL 参数（可选）
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# 修改 ExpCookieURL 参数（可选）{#modifying-the-expcookieurl-paramter-optional}

{{eol}}

ExpCookieURL参数可用于测试受控实验是否正常工作。

此参数定义虚拟页面的URL，如果收到请求，虚拟页面会将您放入指定的实验和组，然后将您重定向到网站的根。 从那个点到实验结束，您是指定实验和组的一部分。

此参数的默认页面为 [!DNL setcookie.htm]，但您可以使用任何有效的虚拟URL。

>[!NOTE]
>
>这必须是虚拟URL，不得是真实页面或一段现有内容。 Web服务器上指定路径上不应存在具有指定名称的文件。

以下是ExpCookieURL参数的示例：

[!DNL ExpCookieURL /setcookie.htm]
