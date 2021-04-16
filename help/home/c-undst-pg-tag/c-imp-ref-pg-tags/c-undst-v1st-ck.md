---
description: 网站使用cookies来唯一识别网站的访客，并跟踪其行为。
title: 了解 v1st Cookie
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# 了解 v1st Cookie{#understanding-the-v-st-cookie}

网站使用cookies来唯一识别网站的访客，并跟踪其行为。

当特定浏览器(被视为访客)首次请求您的网站时，[!DNL Sensor]会与您的Web服务器一起设置永久cookie，cs(cookie)(v1st)，在系统内部解释为x-trackingid。 此永久Cookie是除您的站点可能设置的任何其他Cookie之外设置的。 此Cookie可优化您在多个会话上跟踪访客的能力，从而支持许多类型的分析，否则这些类型是不可能实现的。

[!DNL Sensor] 在cookie中分配一个64位数字键，以标识将站点请求作为唯一标识符的新访客。当[!DNL Sensor]看到来自浏览器的请求时，它会检查请求数据中是否存在“cs(cookie)(v1st)”（由[!DNL Sensor]设置的第一方永久Cookie）。 如果cs(cookie)(v1st)不存在，[!DNL Sensor]会通过Web服务器通知浏览器设置它。 与其他解决方案不同，[!DNL Sensor]能够在访客的第一个请求上设置此Cookie。

以下是Web服务器在浏览器第一次访问您的站点时，以[!DNL Sensor]的方向发送给浏览器的标准永久Cookie头。 如果需要其他名称或到期日期，可以在配置时定义格式。 例如：

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

该Cookie仅设置一次，即在该访客向您的网站发出的第一个请求中。 然后，当浏览器将来每次对您的网站发出请求（页面或嵌入对象请求）时，都会从该访客中收集该内容。 Cookie的大小非常小，可最大限度地减少将Cookie从浏览器发送到站点的每个请求发送到服务器的带宽。

接受永久Cookie由浏览器自行决定。 大多数Web用户都了解Cookie的作用，并认识到第一方Cookie为他们提供了宝贵的优势，使网站内容能够根据他们的偏好进行自定义。 这些第一方Cookie不会被常用浏览器的默认安全设置阻止。 如果用户确实选择阻止第一方Cookie，则其页面视图请求仍会记录，但来自这些请求的测量数据无法可靠地与站点上的特定访客或其会话关联。 许多网站（尤其是复杂的动态网站）已经使用了第一方Cookie，在许多情况下，这些Cookie是使Web应用程序能够为访客运行所必需的。 从永久Cookie后退一步是会话Cookie，它允许一系列请求联合到一个会话中，但不允许会话间访客跟踪。 [!DNL Site] 能够根据会话cookie或IP号对访客分析进行会话化，但这两种方法都显着降低了可以与或任何其他web活动分析和报告系统 [!DNL Site] 进行的的类型和值。
