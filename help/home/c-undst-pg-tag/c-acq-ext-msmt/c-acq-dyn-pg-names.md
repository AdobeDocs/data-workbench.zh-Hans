---
description: 对于某些网站，需要使用嵌入式对象请求将信息传递到Web服务器，以便传感器可以获取有关实际提供的页面的详细信息，并用于报告和分析。
title: 获取动态页面名称
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# 获取动态页面名称{#acquiring-dynamic-page-names}

对于某些网站，需要使用嵌入式对象请求将信息传递到Web服务器，以便传感器可以获取有关实际提供的页面的详细信息，并用于报告和分析。

如果Web服务器所看到的页面URL不表示向浏览器显示的页面内容，则可能需要此参数。 这种情况通常是由于使用个性化或动态内容管理系统所致，在这些系统中，页面中提供的实际内容是通过URL、Cookie、相关数据和应用程序逻辑动态确定的。

实施嵌入式对象以收集其他测量应该对网站的整体性能影响很小。 Adobe建议您嵌入JavaScript文件作为用于收集扩展属性的对象。 （请注意，JavaScript文件可以嵌入，而不会因使用嵌入图像而对网页的布局和呈现方式产生任何潜在影响。） 为了准确捕获嵌入对象内传递的信息，Adobe还建议使用通用名称。 出于命名目的，Adobe将此对象称为[!DNL zig.js]。 [!DNL zig.js]文件应在安装[!DNL Sensor]的Web服务器上的相应目录内创建。 此文件需要存在，以便请求不返回404错误代码。 文件本身的内容并不重要。 您应使用名为[!DNL zig.js]的空白文件，以最大限度地减少因请求而产生的网络流量。

为了[!DNL Sensor]收集实际提供的页面的可用名称，必须向要跟踪或要向其添加唯一页面名称的动态页面中添加几行JavaScript代码。 此代码在页面中嵌入了JavaScript代码片段，这会导致在页面加载时向Web服务器发出第三个嵌入式对象请求。 该请求会将提供的特定页面的详细信息发送回Web服务器。 实际提供的页面名称将作为嵌入对象（在本例中为JavaScript）请求的查询字符串中的变量返回到Web服务器。

通常，嵌入在每个此类HTML页面中的对象请求应如下所示：

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] 确保记 [!DNL Sensor] 录请求，尽管存在相反的 [!DNL Sensor] 内容类型过滤规则，例如在存储JavaScript请求和图像请求之前先对其进行过滤。声明的v_pn变量标识所提供实际页面内容的名称，以便[!DNL Site]知道访客实际查看的页面名称。 v_pn值可以手动或通过其他脚本或应用程序代码建立。

在收集值后，您可以将Data Workbench Server配置为使用附加到[!DNL zag.gif] URI中的查询字符串变量（例如，v_pn=Application Form）的内容（例如，[!DNL https://www.mysite.com/pageserved.asp?v_pn=Application%20Form]）作为[!DNL zag.gif] URI的增强。 除了通过每个HTTP请求获得的基线测量之外，还将通过此请求获得扩展测量。

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_pn= | 与v_pn查询字符串变量关联的值 | v_pn=应用程序表单 |
