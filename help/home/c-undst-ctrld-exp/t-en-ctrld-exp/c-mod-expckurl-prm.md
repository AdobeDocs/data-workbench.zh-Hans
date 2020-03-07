---
description: ExpCookieURL参数可用于测试受控实验是否正常工作。
solution: Insight,Analytics
title: 修改ExpCookieURL参数（可选）
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改ExpCookieURL参数（可选）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURL参数可用于测试受控实验是否正常工作。

此参数定义虚拟页面的URL，该URL在请求时将您放入指定的实验和组中，然后重定向到网站的根目录。 从那一点到实验结束，您是指定实验和组的一部分。

此参数的默认页面是， [!DNL setcookie.htm]但您可以使用任何有效的虚拟URL。

>[!NOTE]
>
>这必须是虚拟URL，并且不能是实际页面或现有内容。 在Web服务器上，在指定路径上不应存在具有指定名称的文件。

以下是ExpCookieURL参数的示例：

[!DNL ExpCookieURL /setcookie.htm]
