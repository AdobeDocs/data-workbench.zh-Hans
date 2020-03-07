---
description: 有关第三方标记和使用P3P防止cookie阻止的概念性信息。
solution: Analytics
title: 第三方页面标记的P3P注意事项
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 第三方页面标记的P3P注意事项{#p-p-considerations-for-third-party-page-tagging}

有关第三方标记和使用P3P防止cookie阻止的概念性信息。

## 了解第三方页面标记 {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

在大多数实施中，Adobe永久Cookie被视为第一方Cookie。 第一方Cookie定义为与主机域关联的Cookie。

假设用户访问http://www.example.com/。 假定传感器已安装并可运行在承载该域的Web服务器上，则Adobe永久cookie将被设置并视为第一方cookie。 但是，您可能希望通过使用嵌入式对象从第三方站点收集测量数据，这些对象是从您正在运行的服务器而不是从承载页面或广告程序的第三方服务器请求并加载的。 [!DNL Sensor] 例如，http://www.example2.com/提供网页，其中提供http://www.example.com/提供的嵌入式对象请求。 http://www.example.com/对嵌入对象的请求导致设置cookie;但是，在这种情况下，Web浏览器或用户代理将Cookie作为第三方Cookie来查看。

在较新的Web浏览器（如Microsoft IE6）中，隐私功能会根据Cookie的压缩策略过滤Cookie，这些压缩策略从Web服务器的HTTP响应头中发送。 在大多数用户从不更改的默认IE6设置中，当第三方Cookie不存在或不能令人满意的压缩策略时，将阻止它们。 大多数遇到Cookie阻止问题的站点在其站点上有第三方Cookie，这些第三方Cookie在HTTP响应头中没有发送相应的压缩策略。 此外，当站点被其他站点构建时，会出现一些cookie阻止问题。 例如，作为在线购物门户的一部分的在线商店可能显示在门户提供的框架中。 从浏览器的角度看，当门户设置框架时，商店内容可能显示为第三方内容。 但是，如果访客不通过门户而直接进入在线商店，则内容将是第一方内容。 因此，在线商店发现只有当访客通过门户进入时，他们的Cookie才会被阻止。

基于Web的邮件系统也会造成类似的问题。 如果网站访问者将网页通过电子邮件发送给使用基于Web的邮件系统的朋友，则电子邮件将作为第三方内容显示给朋友的浏览器，因为该内容由电子邮件系统构成框架。 如果有任何与通过电子邮件发送的页面关联的cookie，则IE6会将其视为第三方cookie。

## 使用P3P防止Cookie阻止 {#section-96831cad887649f295aec6931750e41a}

P3P为网站提供了一种标准方式，以计算机可读的XML格式对其隐私策略进行编码。 支持P3P的Web浏览器和其他P3P用户代理会自动获取P3P隐私策略，对其进行解析，并将其与用户的隐私首选项进行比较。

要防止IE6阻止您网站上的cookies，您需要确保：

1. 正在第三方上下文中设置的所有Cookie都与它们关联有P3P压缩策略。
1. 使用自定义HTTP响应头发送相应的压缩策略。
1. IE6认为这些紧凑政策令人满意。
1. 如果第三方Cookie是由另一家公司设置的，您可能需要要求他们启用P3P并设置P3P紧凑策略。 任何设置P3P紧凑策略的主机都必须具有相应的完整P3P策略。 用户可以更改其IE6设置，以便在其他条件下也阻止cookie;但是，将令人满意的压缩策略放置到第三方Cookie上可防止大多数IE6 Cookie阻止。

以下是此类P3P头的示例：

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

在本例中，该文件用于引用驻留在Web服务器上的关联文件，该文件表示您的网站收集的信息类型、您的组织所遵循的争议解决方法、所收集数据的使用方式、数据的拥有者以及与因特网隐私相关的其他标准信息。 [!DNL p3p.xml][!DNL policy.xml] “CP”后面的三个字符代码是模拟文件中所述内容的压缩策略代 [!DNL policy.xml] 码。

所有压缩的策略和策略XML文件都应针对所部署的组织进行定制，准确指定其网站数据收集的内部隐私策略。 您可以在线找到大量P3P策略编辑器，以及有关在网站中实施适当隐私策略的更深入的信息。

有关Internet Explorer 6如何处理P3P标题的更多信息，请访问：

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
