---
description: 网站使用cookies来唯一识别您网站的访客，并跟踪其随时间的行为。
solution: Analytics
title: 了解v1st Cookie
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解v1st Cookie{#understanding-the-v-st-cookie}

网站使用cookies来唯一识别您网站的访客，并跟踪其随时间的行为。

特定浏览器（视为访客）首次请求您的网站时， [!DNL Sensor] Web服务器会与您的Web服务器一起设置永久cookie, cs(cookie)(v1st)，在系统内部解释为x-trackingid。 此永久Cookie是除了您的站点可能设置的任何其他Cookie之外设置的。 此Cookie可优化您在多个会话中跟踪访客的能力，从而支持许多类型的分析，否则这些分析是不可能的。

[!DNL Sensor] 在cookie中分配一个64位数字键，以标识将站点请求作为唯一标识符的新访客。 当浏 [!DNL Sensor] 览器显示请求时，它检查请求数据中是否存在“cs(cookie)(v1st)”(由设置的第一方永久 [!DNL Sensor]cookie)。 如果cs(cookie)(v1st)不存在，则通过 [!DNL Sensor]Web服务器通知浏览器设置它。 与其他解决方 [!DNL Sensor] 案不同，能够在访客的第一个请求中设置此Cookie。

下面是Web服务器在浏览器第一次请求您的站点时按方向发送给浏览器的标准永久Cookie头 [!DNL Sensor]。 如果需要其他名称或到期日期，可以在配置时定义格式。 例如：

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

该Cookie仅在访客首次向您的网站发出请求时设置一次。 然后，在将来浏览器每次向您的站点发出请求（页面或嵌入对象请求）时，都会从该访客收集该访客。 Cookie的大小非常小，可使每次从浏览器向站点发送请求时向服务器发送Cookie的带宽最小。

接受永久Cookie由浏览器自行决定。 大多数Web用户都了解Cookie的用途，并认识到第一方Cookie为他们提供了有价值的好处，允许根据他们的偏好自定义网站内容。 这些第一方Cookie不会被常用浏览器的默认安全设置阻止。 如果用户确实选择阻止第一方Cookie，则其页面查看请求仍会记录，但这些请求中的测量数据无法可靠地与站点上的特定访客或其会话关联。 许多网站（尤其是复杂的动态网站）已经使用第一方Cookie，这在很多情况下是使Web应用程序能够为访客运行所必需的。 从永久Cookie中回退的步骤是会话Cookie，它允许一系列请求组合到一个会话中，但不允许会话间访客跟踪。 [!DNL Site] 能够根据会话cookie或IP号对访客数据进行会话化，但这两种方法都显着降低了可通过或任何其他Web活动分析和报告系统进行分析的类型 [!DNL Site] 和价值。
