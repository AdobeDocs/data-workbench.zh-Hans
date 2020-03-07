---
description: 典型的网站配置使用cookies来唯一识别您网站的访客并跟踪访客随时间的变化。
solution: Insight,Analytics
title: 网站如何识别访客？
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 网站如何识别访客？{#how-does-site-identify-visitors}

典型的网站配置使用cookies来唯一识别您网站的访客并跟踪访客随时间的变化。

特定浏览器（视为访客）首次请求您的网站时，会与Web服务器一起设置永久Cookie(默认情况下 [!DNL Sensor] )，该Cookie在系统内部解释为 [!DNL cs(cookie)(v1st)][!DNL x-trackingid]。 该Cookie仅在访客向您的网站发出的第一个请求中设置一次。 然后，将来每次浏览器请求您网站的请求（页面或嵌入对象请求）时，都会从该访客收集该访客。

接受永久Cookie由浏览器自行决定。 如果用户确实选择阻止永久Cookie，则其页面查看请求仍会被记录，但这些请求中的测量数据不会与某个特定访客或他们在网站上的会话相关联，除非您实施了访客识别的替代方法，如在IP和UserAgent字段上使用哈希转换。

>[!NOTE]
>
>只有在数据集中才能分析站点实验，其中唯一使用的访客识别方法是集合的永 [!DNL Sensor] 久cookie方法。 在J2EE服务器（JBoss、Tomcat、WebLogic和WebSphere）上运行的传感器不支持受控试验。

在受控实验期间，不接受cookie的用户可以通过一次点击放置在不同的实验组中。 仅当在关闭了“中断会话过滤器”的情况下执行测试分析时，这才会成为问题， [!DNL Insight]Adobe不建议这样做。

有关“中断的会话过滤器”的详细信息，请参阅* [!DNL Insight] 用户指南*。

如果访客在实验期间清除Cookie，则会为该访客分配一个新的Cookie，并且可能会将该Cookie分配给其他组。 由于Adobe将访客识别为新访客，因此该实验不会失效。
