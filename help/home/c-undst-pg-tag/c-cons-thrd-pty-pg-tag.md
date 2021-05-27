---
description: 有关使用P3P标记和防止Cookie阻塞的概念信息。
title: 第三方页面标记的 P3P 注意事项
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# 第三方页面标记的 P3P 注意事项{#p-p-considerations-for-third-party-page-tagging}

有关使用P3P标记和防止Cookie阻塞的概念信息。

## 了解第三方页面标记{#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

在大多数实施中，Adobe永久Cookie被视为第一方Cookie。 第一方Cookie被定义为与主机域关联的Cookie。

假设用户访问http://www.example.com/。 假设在托管该域的Web服务器上安装了传感器并且该传感器可运行，则会设置Adobe永久Cookie并将其视为第一方Cookie。 但是，您可能希望通过使用嵌入式对象从第三方站点收集测量数据，这些对象是从运行[!DNL Sensor]的服务器中请求并加载的，而不是从托管页面或广告程序的第三方服务器中加载的。 例如，http://www.example2.com/提供网页，其中提供http://www.example.com/中提供的嵌入对象请求。 从http://www.example.com/请求嵌入对象会导致设置Cookie;但是，在此上下文中，Web浏览器或用户代理将Cookie视为第三方Cookie。

在较新的Web浏览器（如Microsoft IE6）中，隐私功能会根据Cookie在Web服务器的HTTP响应标头中发送的压缩策略来过滤Cookie。 在大多数用户从不更改的默认IE6设置中，当第三方Cookie不存在或不符合要求的紧凑策略时，将会阻止这些Cookie。 大多数遇到Cookie拦截问题的网站的第三方Cookie在其网站上没有在HTTP响应标头中发送相应的压缩策略。 此外，当网站被另一个网站构建时，会出现一些Cookie阻止问题。 例如，作为在线购物门户一部分的在线商店可能显示在该门户提供的框架中。 从浏览器的角度来看，商店内容在门户设置框架时可能显示为第三方内容。 但是，如果访客直接转到在线商店而没有通过门户，则内容将是第一方内容。 因此，在线商店发现，只有当访客通过门户进入时，其Cookie才会被阻止。

基于Web的邮件系统会导致类似的问题。 如果网站访客通过电子邮件将网页发送给使用基于Web的邮件系统的好友，则该电子邮件会作为第三方内容显示在好友的浏览器中，因为该内容是由电子邮件系统构建的。 如果存在任何与通过电子邮件发送的页面关联的Cookie，则IE6会将它们视为第三方Cookie。

## 使用P3P防止Cookie阻塞{#section-96831cad887649f295aec6931750e41a}

P3P为网站提供了一种标准方式，以计算机可读的XML格式对其隐私政策进行编码。 启用P3P的Web浏览器和其他P3P用户代理会自动获取、解析P3P隐私政策，并将其与用户的隐私首选项进行比较。

要阻止IE6阻止您网站上的Cookie，您需要确保：

1. 在第三方上下文中设置的所有Cookie都与其关联P3P紧凑策略。
1. 使用自定义HTTP响应标头发送相应的压缩策略。
1. IE6认为这些契约政策令人满意。
1. 如果第三方Cookie是由其他公司设置的，您可能需要要求他们启用P3P并设置P3P紧凑策略。 任何设置P3P紧凑策略的主机也必须具有相应的完整P3P策略。 用户可以更改其IE6设置，以便在其他情况下也会阻止Cookie;但是，对第三方Cookie放置令人满意的紧凑策略可防止大多数IE6 Cookie阻塞。

以下是此P3P头的示例：

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

在此示例中，文件[!DNL p3p.xml]用于引用驻留在Web服务器上的关联[!DNL policy.xml]文件，该文件表示您的网站收集的信息类型、您的组织遵守的争议解决方法、收集的数据的使用方式、数据的拥有者以及与Internet隐私相关的其他标准信息。 “CP”后面的三个字符代码是用于模拟[!DNL policy.xml]文件中所述内容的压缩策略代码。

所有紧凑的策略和策略XML文件都应针对其所部署的相应组织进行定制，以准确指定与网站数据收集有关的内部隐私政策。 您可以在线找到许多P3P政策编辑者，以及与在您的网站中实施适当隐私政策相关的更深入的信息。

有关Internet Explorer 6如何处理P3P标头的详细信息，请访问：

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
