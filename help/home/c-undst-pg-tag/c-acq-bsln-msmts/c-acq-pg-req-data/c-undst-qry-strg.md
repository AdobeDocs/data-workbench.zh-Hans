---
description: 由于HTTP的无状态性质，查询字符串(cs-uri-query)通常由Web应用程序和站点开发人员用于在页面之间传递信息。
title: 了解查询字符串
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# 了解查询字符串{#understanding-the-query-string}

{{eol}}

由于HTTP的无状态性质，查询字符串(cs-uri-query)通常由Web应用程序和站点开发人员用于在页面之间传递信息。

在很多情况下，当信息被 [!DNL Sensor] 在web服务器上。 此类信息可供 [!DNL Site] 以阐明网站的真实结构、访客通过网站的路径以及其他信息。

在某些动态网站中，查询字符串中的名称=值对（变量）对于确定访客请求的实际页面很重要。 在这种情况下，URL可以采用以下或类似的方式来构建：

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

在此示例中，PAGENAME实际上是向此URL的请求者提供哪个页面的指示器。 许多网络日志分析工具和服务限制了网站操作员根据网站URL查询字符串中出现的查询字符串变量来定义其网站中页面的功能。 Data Workbench Server和Data Workbench可以配置为使用此类查询名称来定义唯一页面。 这很重要，因为许多系统会将以下URL解释为同一页面，但 [!DNL Site] 不会。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
https://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同样，网站开发人员和应用程序通常会向网站的URL中添加许多查询字符串变量，这些变量与识别所请求的实际页面无关。 示例如下：

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

在此示例中，查询字符串变量CAMPAIGN=已添加到URL中。 此CAMPAIGN变量用于指示哪些营销活动导致访客选择此URL。 [!DNL Site] 可以配置为使用此CAMPAIGN信息，但将其与访客查看的页面定义分开，以便在用于报告和分析的页面列表中，您只需看到以下内容：

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
