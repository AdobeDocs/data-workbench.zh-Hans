---
description: 典型的网站配置使用cookies来唯一识别网站的访客并跟踪其随时间的行为。
solution: Analytics,Analytics
title: 网站如何识别访客？
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---


# 网站如何识别访客？{#how-does-site-identify-visitors}

典型的网站配置使用cookies来唯一识别网站的访客并跟踪其随时间的行为。

特定浏览器(视为访客)首次请求您的网站时，会与Web服务 [!DNL Sensor] 器一起设置永久cookie（默认情况下），该cookie在系统内部 [!DNL cs(cookie)(v1st)]解释为 [!DNL x-trackingid]。 该Cookie仅设置一次，即在该访客向您的网站发出的第一个请求中。 随后，将来每次浏览器请求您的网站（页面或嵌入对象请求）时，都会从该访客收集该内容。

接受永久Cookie由浏览器自行决定。 如果用户确实选择阻止永久性Cookie，则其页面视图请求仍会记录，但这些请求中的测量数据与特定访客或其在网站上的会话不相关，除非您实施了访客标识的替代方法，如在IP和UserAgent字段上使用哈希转换。

>[!NOTE]
>
>只有在数据集中才能分析站点实验，其中唯一使用的访客识别方法是集 [!DNL Sensor] 合的永久cookie方法。 在J2EE服务器（JBoss、Tomcat、WebLogic和WebSphere）上运行的传感器不支持受控试验。

在受控实验期间，不接受cookie的用户可以从一次点击到下一次放入不同的实验组。 仅当在关闭中断会话过滤器的情况下执行测试分析时，此问题才会变 [!DNL Insight]为问题，不建议使用此Adobe。

有关中断会话过滤器的详细信息，请参阅* [!DNL Insight] 用户指南*。

如果访客在实验过程中清除Cookie，则访客会被分配一个新的Cookie，并且可能会被分配给其他组。 由于Adobe将访客标识为新的，因此实验不会失效。
