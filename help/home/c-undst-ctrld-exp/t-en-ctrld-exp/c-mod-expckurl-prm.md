---
description: ExpCookieURL参数可用于测试受控实验是否正常工作。
solution: Analytics,Analytics
title: 修改 ExpCookieURL 参数（可选）
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# 修改 ExpCookieURL 参数（可选）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURL参数可用于测试受控实验是否正常工作。

此参数定义虚拟页面的URL，当请求时，该URL会将您放置到指定的实验和组中，然后将您重定向到网站的根。 从那个点到实验结束，您是指定实验和组的一部分。

此参数的默认页为[!DNL setcookie.htm]，但您可以使用任何有效的虚拟URL。

>[!NOTE]
>
>这必须是虚拟URL，不得是实际页面或现有内容。 在Web服务器上，在指定路径上不应存在具有指定名称的文件。

以下是ExpCookieURL参数的示例：

[!DNL ExpCookieURL /setcookie.htm]
