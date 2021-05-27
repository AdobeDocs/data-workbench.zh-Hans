---
description: 网站使用Cookie来唯一识别网站的访客，并跟踪他们在一段时间内的行为。
title: 了解 v1st Cookie
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# 了解 v1st Cookie{#understanding-the-v-st-cookie}

网站使用Cookie来唯一识别网站的访客，并跟踪他们在一段时间内的行为。

当特定浏览器（被视为访客）首次向您的网站提出请求时， [!DNL Sensor]会与您的Web服务器一起设置永久性Cookie， cs(cookie)(v1st)，该Cookie在系统内部解释为x-trackingid。 此永久Cookie是在您的网站可能设置的任何其他Cookie之外设置的。 此Cookie可优化您在多个会话中跟踪访客的功能，从而支持许多类型的分析，否则这些分析将无法实现。

[!DNL Sensor] 在cookie中分配64位数字键，以识别向网站提出请求作为唯一标识符的新访客。当[!DNL Sensor]看到来自浏览器的请求时，它会检查请求数据中是否存在“cs(cookie)(v1st)”（由[!DNL Sensor]设置的第一方永久Cookie）。 如果cs(cookie)(v1st)不存在，[!DNL Sensor]会通过Web服务器告知浏览器设置它。 与其他解决方案不同，[!DNL Sensor]能够在访客的第一个请求中设置此Cookie。

以下是Web服务器在浏览器第一次请求您的网站时向浏览器发送的标准永久性Cookie标头，其方向为[!DNL Sensor]。 如果需要其他名称或过期日期，可在配置时定义格式。 例如：

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

该Cookie仅设置一次，即在该访客首次向您的网站发出请求时。 然后，系统会在以后每次浏览器对您的网站提出请求（页面或嵌入的对象请求）时，从该访客收集该数据。 Cookie的大小非常小，可最大限度地减少在从浏览器向网站发送每个请求时，将其传输到服务器的带宽量。

接受永久Cookie由浏览器自行决定。 大多数Web用户都了解Cookie的功能，并认识到第一方Cookie在允许根据自己的偏好自定义网站内容方面为他们提供了宝贵的优势。 通用浏览器的默认安全设置不会阻止这些第一方Cookie。 如果用户选择阻止第一方Cookie，则其页面查看请求仍会被记录，但来自这些请求的测量数据无法可靠地与特定访客或其网站上的会话关联。 许多网站（尤其是复杂的动态网站）已经使用了第一方Cookie，在许多情况下，这些Cookie是使Web应用程序能够为访客运行所必需的。 永久Cookie的后退一步是会话Cookie，它允许将一系列请求编组到一个会话中，但不允许会话间访客跟踪。 [!DNL Site] 能够根据会话cookie或IP号对访客数据进行会话化，但是这两种方法都会显着降低可以与或任何其他web活动分析和报告系统 [!DNL Site] 进行的分析类型和价值。
