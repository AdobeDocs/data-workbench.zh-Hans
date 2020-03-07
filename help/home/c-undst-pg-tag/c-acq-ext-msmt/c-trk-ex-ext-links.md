---
description: 捕获第三方网站链接中的活动以启用退出目标分析。
solution: Analytics
title: 跟踪外部链接的退出情况
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 跟踪外部链接的退出情况{#tracking-exits-to-external-links}

捕获第三方网站链接中的活动以启用退出目标分析。

网页可包含指向第三方网站的链接，并且可以捕获这些链接中的活动以启用退出目标分析，尤其是在第三方网站负责在收到此类引用时支付引用费用的情况下。 由于单击事件默认写入第三方系统的日志文件，因此需要对链接进行修改，以便在本地捕获单击事件。 您网站中存在的第三方链接必须修改如下：

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

必须创 [!DNL PageExit.htm] 建引用的文件，并且应将其结构化为包含以下脚本：

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

通过对文件发出请 [!DNL PageExit.htm] 求，收集v_eurl值以用于分析目的。 此外，加 [!DNL PageExit.htm] 载后，它会立即重定向到指定的v_eurl目标位置。

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_eurl | 与v_eurl查询字符串变量关联的值。 此值表示HTML页面中存在的链接的目标URL。 | v_eurl=www.othersite.com |

