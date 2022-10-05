---
description: 使用JavaScript文档对象模型，可以使用其他脚本方法来增加zig.js文件的请求。
title: 获取文档对象
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# 获取文档对象{#acquiring-document-objects}

{{eol}}

使用JavaScript文档对象模型，可以使用其他脚本方法来增加zig.js文件的请求。

META标记值、DIV标记的ID值等信息可由名称引用并收集为变量以用于分析。 例如，要动态捕获HTML文档的META元素中包含的信息，可以使用以下JavaScript语法：

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_1"] = metacontent;
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1= | 与METAVALUE查询字符串变量关联的值。 此值表示HTML文档META元素内的数据。 | v_1=此页面提供与感谢订单页面相关的内容。 |

收集数据后，您可以配置Data Workbench Server以处理此测量数据，以便进行分析和报告。
