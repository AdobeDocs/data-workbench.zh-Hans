---
description: 对于某些站点，必须使用嵌入式对象请求将信息传递到Web服务器，这样传感器才能获取关于实际服务的页面的详细信息并用于报告和分析。
solution: Analytics
title: 获取动态页面名称
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 获取动态页面名称{#acquiring-dynamic-page-names}

对于某些站点，必须使用嵌入式对象请求将信息传递到Web服务器，这样传感器才能获取关于实际服务的页面的详细信息并用于报告和分析。

如果Web服务器所看到的页面URL不指示显示给浏览器的页面内容，则可能需要此设置。 这种情况通常是由于使用个性化或动态内容管理系统，其中页面中提供的实际内容由URL、cookie、相关数据和应用程序逻辑动态确定。

实施嵌入式对象以收集其他度量值时对网站整体性能的影响应最小。 Adobe建议您嵌入一个JavaScript文件作为用于收集扩展属性的对象。 （请注意，JavaScript文件可以嵌入，而不会因使用嵌入图像而对网页的布局和显示产生任何潜在影响。）为准确捕获嵌入对象中传递的信息，Adobe还建议使用通用名称。 为便于命名，Adobe将此对象称为 [!DNL zig.js]。 应 [!DNL zig.js] 该在安装了Web服务器的相应目录中创建 [!DNL Sensor] 文件。 此文件需要存在，以便请求不返回404错误代码。 文件本身的内容并不重要。 您应使用名为的空文件， [!DNL zig.js] 以最大限度地减少因请求产生的网络流量。

要 [!DNL Sensor] 收集实际提供的页面的可用名称，必须向要跟踪或要向其添加唯一页面名称的动态页面添加几行JavaScript代码。 此代码在页面中嵌入JavaScript代码片段，这会导致在加载页面时向Web服务器发出第三个嵌入式对象请求。 该请求将提供的特定页面的详细信息发送回Web服务器。 实际服务的页面名称作为嵌入对象（本例中为JavaScript）请求的查询字符串中的变量返回到Web服务器。

通常，嵌入到每个此类HTML页面的对象请求应如下所示：

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] 确保 [!DNL Sensor] 记录请求，尽管存在相反的内容类 [!DNL Sensor] 型过滤规则，如在存储JavaScript和图像请求之前过滤掉它们。 声明的v_pn变量标识所提供的实际页面内容的名称，以便 [!DNL Site] 知道访客实际查看的页面的名称。 v_pn值可以手动建立，也可以通过其他脚本或应用程序代码建立。

收集值后，您可以配置Data Workbench Server以使用附加到 [!DNL zag.gif] URI(例如， [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form])的查询字符串变量（name=value对，例如v_pn=Application Form）的内容作为 [!DNL zag.gif] URI的增强。 除了通过每个HTTP请求获取的基线测量之外，还将通过此请求获取扩展测量。

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_pn= | 与v_pn查询字符串变量关联的值 | v_pn=应用程序表单 |

