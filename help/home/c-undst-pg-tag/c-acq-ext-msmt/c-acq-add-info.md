---
description: 查询字符串变量可添加到JavaScript请求中，以在发出请求时收集其他测量。
title: 获取其他信息
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
exl-id: ad4f5e08-b7b7-4de3-b0c2-71440facb2d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# 获取其他信息{#acquiring-additional-information}

{{eol}}

查询字符串变量可添加到JavaScript请求中，以在发出请求时收集其他测量。

这些变量可以手动添加，也可以通过页面本身中的脚本添加。

可以通过脚本从页面获取的其他信息可以通过以下代码作为示例添加到嵌入式对象中：

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
v["_1"] = “99.99”;
v["_2"] = "visa";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>
<noscript>

<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>
<!-- END REFERENCE PAGE TAG-->
```

在此示例中，v_1和v_2的脚本变量可以从网页中的其他函数派生。 已作为示例插入变量。 除了随每个请求获得的基线测量之外，还将根据上述URL的请求获得以下扩展测量：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_pn= | 与v_pn查询字符串变量关联的值 | v_pn=应用程序表单 |
| v_1= | 与v_1查询字符串变量关联的值 | v_1=99.99 |
| v_2= | 与v_2查询字符串变量关联的值 | v_2=visa |
