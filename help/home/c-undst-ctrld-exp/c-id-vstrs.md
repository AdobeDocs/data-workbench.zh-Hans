---
description: 网站的典型配置使用Cookie来唯一识别网站的访客并跟踪其随时间的行为。
solution: Analytics
title: 网站如何识别访客？
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# 网站如何识别访客？{#how-does-site-identify-visitors}

{{eol}}

网站的典型配置使用Cookie来唯一识别网站的访客并跟踪其随时间的行为。

特定浏览器（被视为访客）首次请求您的网站时， [!DNL Sensor] 可与Web服务器一起设置永久性Cookie（默认情况下） [!DNL cs(cookie)(v1st)])，在系统内部解释为 [!DNL x-trackingid]. 该Cookie仅设置一次，即在该访客首次向您的网站发出请求时。 然后，系统会在以后每次浏览器对您的网站提出请求（页面或嵌入的对象请求）时，从该访客收集该数据。

接受永久Cookie由浏览器自行决定。 如果用户选择阻止永久性Cookie，则其页面查看请求仍会被记录，但来自这些请求的测量数据不会与特定访客或他们在网站上的会话相关联，除非您实施了访客标识的替代方法，例如在IP和UserAgent字段中使用哈希转换。

>[!NOTE]
>
>网站实验只能在使用唯一访客识别方法( [!DNL Sensor] 设置永久cookie方法。 在J2EE服务器（JBoss、Tomcat、WebLogic和WebSphere）上运行的传感器不支持对照实验。

在对照实验中，不接受Cookie的用户可以从一次点击到下一次，置于不同的实验组中。 仅当您在禁用中断会话过滤器的情况下执行测试分析时，此问题才会出现 [!DNL Insight]，不建议使用此Adobe。

有关中断会话过滤器的更多信息，请参阅* [!DNL Insight] 用户指南*。

如果访客在实验期间清除了Cookie，则会为访客分配一个新Cookie，并且可能会将该Cookie分配给其他组。 由于Adobe将访客标识为新访客，因此实验不会失效。
