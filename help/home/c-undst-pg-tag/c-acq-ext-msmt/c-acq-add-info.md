---
description: 查询字符串变量可以添加到JavaScript请求中，以在发出请求时收集其他度量。
solution: Analytics
title: 获取其他信息
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 获取其他信息{#acquiring-additional-information}

查询字符串变量可以添加到JavaScript请求中，以在发出请求时收集其他度量。

这些变量可以手动添加，也可以通过页面本身中的脚本添加。

例如，可以通过脚本将可以从页面获取的附加信息添加到嵌入式对象中：

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

在此示例中，v_1和v_2的脚本变量可从网页中的其他函数派生。 变量已作为示例插入。 除了每次请求获得的基线测量值之外，还将获得以下扩展测量值，并应上述URL的请求：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_pn= | 与v_pn查询字符串变量关联的值 | v_pn=应用程序表单 |
| v_1= | 与v_1查询字符串变量关联的值 | v_1=99.99 |
| v_2= | 与v_2查询字符串变量关联的值 | v_2=visa |

