---
description: 网站的典型配置使用cookies来唯一识别网站的访客并跟踪其行为。
solution: Analytics,Analytics
title: 网站如何识别访客？
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# 网站如何识别访客？{#how-does-site-identify-visitors}

网站的典型配置使用cookies来唯一识别网站的访客并跟踪其行为。

当特定浏览器(被视为访客)首次请求您的网站时，[!DNL Sensor]会与您的Web服务器一起设置永久Cookie（默认情况下为[!DNL cs(cookie)(v1st)]），在系统内部解释为[!DNL x-trackingid]。 该Cookie仅设置一次，即在该访客向您的网站发出的第一个请求中。 随后，将在将来浏览器每次对您的网站发出请求（页面或嵌入对象请求）时从该访客收集该内容。

接受永久Cookie由浏览器自行决定。 如果用户确实选择阻止永久Cookie，则其页面视图请求仍会记录，但来自这些请求的测量数据不会与特定访客或其在网站上的会话相关，除非您实施了访客标识的替代方法，如在IP和UserAgent字段上使用哈希转换。

>[!NOTE]
>
>站点实验只能在使用中唯一的访客识别方法是[!DNL Sensor]设置永久cookie方法的数据集中进行分析。 在J2EE服务器（JBoss、Tomcat、WebLogic和WebSphere）上运行的传感器不支持受控试验。

在受控实验期间，不接受Cookie的用户可以通过一次点击放置到不同的实验组中。 仅当在[!DNL Insight]中关闭了“中断的会话过滤器”时执行测试分析时，此问题才会变为问题，建议不要使用此Adobe。

有关中断会话过滤器的详细信息，请参见* [!DNL Insight]用户指南*。

如果访客在实验期间清除Cookie，则访客会被分配一个新Cookie，并且可能会被分配到其他组。 由于Adobe将访客标识为新的，因此该实验不会失效。
