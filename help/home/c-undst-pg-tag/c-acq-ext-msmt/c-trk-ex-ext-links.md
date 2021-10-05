---
description: 通过捕获第三方网站链接中的活动以启用退出目标分析。
title: 跟踪外部链接的退出情况
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# 跟踪外部链接的退出情况{#tracking-exits-to-external-links}

通过捕获第三方网站链接中的活动以启用退出目标分析。

网页可以包含指向第三方网站的链接，并且可以捕获这些链接中的活动以启用退出目标分析，特别是当第三方网站在收到此类推荐时负责支付推荐费时。 由于点击事件默认写入第三方系统的日志文件，因此需要对链接进行修改，以便在本地捕获点击事件。 您网站中存在的第三方链接必须按照以下方式进行修改：

```
<A HREF=”https://www.myserver.com/PageExit.htm?v_eurl=https://www.othersite.com”>
```

必须创建引用的[!DNL PageExit.htm]文件，且其结构应包含以下脚本：

```
<html>
<head>

<script>
function getExitURLQuery(variable)
{

var query = window.location.search.substring(1);
var vars = query.split("&");
for (var i=0; i<vars.length; i++)
{
var pair = vars[i].split("=");
if (pair[0] == variable)
{
return pair[1];
}
 }
}
</script>

<script>
location.replace(getExitURLQuery("v_eurl"));
</script>

</head>
</html>
```

通过对[!DNL PageExit.htm]文件提出请求，收集v_eurl值以用于分析。 此外，在加载[!DNL PageExit.htm]时，它会立即重定向到指定的v_eurl目标位置。

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_eurl | 与v_eurl查询字符串变量关联的值。 此值表示HTML页面中存在的链接的目标URL。 | v_eurl=www.othersite.com |
