---
description: 有关第三方标记和使用P3P防止cookie阻塞的概念性信息。
title: 第三方页面标记的 P3P 注意事项
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# 第三方页面标记的 P3P 注意事项{#p-p-considerations-for-third-party-page-tagging}

有关第三方标记和使用P3P防止cookie阻塞的概念性信息。

## 了解第三方页面标记{#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

在大多数实施中，Adobe永久Cookie被视为第一方Cookie。 第一方Cookie被定义为与主机域关联的Cookie。

假设用户访问http://www.example.com/。 假定在托管该域的Web服务器上安装并运行了传感器，则会设置Adobe永久Cookie并将其视为第一方Cookie。 但是，您可能希望通过使用嵌入式对象从第三方站点收集测量数据，这些对象从运行[!DNL Sensor]的服务器(而不是从承载页面或广告项目的第三方服务器)请求并加载。 例如，http://www.example2.com/用于一个网页，其中嵌入的对象请求从http://www.example.com/处理。 来自http://www.example.com/的对嵌入对象的请求导致设置了Cookie;但是，在此上下文中，web浏览器或用户代理将cookie视图为第三方cookie。

在Microsoft IE6等较新的Web浏览器中，隐私功能会根据Cookie的压缩策略筛选Cookie，这些压缩策略是在Web服务器的HTTP响应头中发送的。 在大多数用户从不更改的默认IE6设置中，当第三方Cookie不存在或无法令人满意的压缩策略时，将阻止它们。 大多数遇到Cookie阻止问题的站点在其站点上都有第三方Cookie，这些Cookie在HTTP响应头中没有发送相应的压缩策略。 此外，当站点被另一个站点构建时，会出现一些Cookie阻止问题。 例如，作为在线购物门户的一部分的在线商店可能显示在门户提供的框架中。 从浏览器的角度看，当门户设置框架时，商店内容可能显示为第三方内容。 但是，如果访客直接进入在线商店而不通过门户，则内容将是第一方内容。 因此，网上商店发现，只有当访客通过门户进入时，他们的Cookie才会被阻止。

基于Web的邮件系统也会导致类似的问题。 如果某个网站访客将网页通过电子邮件发送给使用基于Web的邮件系统的朋友，则该电子邮件在朋友的浏览器中显示为第三方内容，因为该内容由电子邮件系统设置框架。 如果有任何与通过电子邮件发送的页面关联的Cookie，则IE6会将其视为第三方Cookie。

## 使用P3P防止Cookie阻塞{#section-96831cad887649f295aec6931750e41a}

P3P为网站提供了一种标准方式，以计算机可读的XML格式对其隐私策略进行编码。 支持P3P的Web浏览器和其他P3P用户代理会自动获取P3P隐私策略，分析这些策略，并与用户的隐私首选项进行比较。

要防止IE6阻止您网站上的Cookie，您需要确保：

1. 在第三方上下文中设置的所有Cookie都具有与其关联的P3P压缩策略。
1. 使用自定义HTTP响应头发送相应的压缩策略。
1. IE6认为这些契约政策令人满意。
1. 如果第三方Cookie由其他公司设置，您可能需要要求他们启用P3P并设置P3P压缩策略。 任何设置P3P压缩策略的主机也必须具有相应的完整P3P策略。 用户可以更改其IE6设置，以便在其他条件下也阻止cookie;但是，将令人满意的压缩策略放置到第三方cookie上可防止大多数IE6 cookie阻止。

以下是此类P3P头的示例：

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

在此示例中，文件[!DNL p3p.xml]用于引用驻留在Web服务器上的关联[!DNL policy.xml]文件，该文件指示您的网站收集的信息类型、您的组织遵循的争议解决方法、所收集数据的使用方式、数据的所有者以及与Internet隐私相关的其他标准信息。 “CP”后面的三个字符代码是模拟[!DNL policy.xml]文件中所述内容的压缩策略代码。

所有简洁的策略和策略XML文件都应针对部署它们的组织进行定制，准确指定它们在网站数据收集方面的内部隐私策略。 您可以在线找到许多P3P策略编辑器，以及有关在您的网站中实施适当隐私策略的详细信息。

有关Internet Explorer 6如何处理P3P头的详细信息，请访问：

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
