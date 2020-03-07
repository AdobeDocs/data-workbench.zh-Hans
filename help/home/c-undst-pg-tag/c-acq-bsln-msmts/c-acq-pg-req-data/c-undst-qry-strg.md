---
description: 由于HTTP的无状态性质，Web应用程序和站点开发人员经常使用查询字符串(cs-uri-query)在页面之间传递信息。
solution: Analytics
title: 了解查询字符串
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解查询字符串{#understanding-the-query-string}

由于HTTP的无状态性质，Web应用程序和站点开发人员经常使用查询字符串(cs-uri-query)在页面之间传递信息。

在很多情况下，当在Web服务器处获取信息时，信息可以在查询字符串 [!DNL Sensor] 中传递。 此类信息可用于说 [!DNL Site] 明网站的真实结构、访客通过网站的路径以及其他信息。

在某些动态网站中，查询字符串中的name=value对（变量）对于确定访客请求的实际页面很重要。 在这种情况下，URL可以采用以下或类似的方式构建：

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

在此示例中，PAGENAME实际上是向此URL的请求者提供哪个页面的指示符。 许多Web日志分析工具和服务限制了站点操作员根据站点URL的查询字符串中出现的查询字符串变量定义其站点中页面的能力。 可以将Data Workbench Server和Data Workbench配置为使用此类查询名称来定义唯一页面。 这很重要，因为许多系统会将以下URL解释为同一页面，但不 [!DNL Site] 会。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同样，站点开发人员和应用程序通常会向站点的URL中添加许多查询字符串变量，这些变量与标识所请求的实际页面无关。 示例如下：

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

在此示例中，查询字符串变量CAMPAIGN=已添加到URL。 此CAMPAIGN变量用于指示哪个营销活动导致访客选择此URL。 [!DNL Site] 可以配置为使用此CAMPAIGN信息，但将其与访客查看的页面的定义分开，这样您只需在页面列表中查看以下内容即可进行报告和分析：

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

