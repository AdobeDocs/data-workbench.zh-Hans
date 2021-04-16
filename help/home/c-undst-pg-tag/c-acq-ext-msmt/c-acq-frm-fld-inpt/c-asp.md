---
description: 网页通常使用ASP(Active Server Pages)编程语言构建。
title: ASP 特定信息
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# ASP 特定信息{#asp-specific-information}

网页通常使用ASP(Active Server Pages)编程语言构建。

ASP是一种在IIS(Internet信息服务)内运行的Microsoft技术。 当浏览器请求ASP文件时，IIS会将该请求传递给ASP引擎。 ASP引擎逐行读取ASP文件，并执行文件中的脚本。 最后，ASP文件作为纯HTML返回到浏览器。 ASP提供RESPONSE或REQUEST对象，除了其他用途外，还允许用户查询或从HTML表单提交的数据的响应或请求。

在某些情况下，您可能不希望将输入到表单中的值附加到URL中，该URL显示在用户浏览器的地址栏中，或在HTML代码本身中可查看。 简单的服务器端JavaScript允许您将表单字段名称及其各自的值附加到日志文件，而无需在用户的浏览器中提供它们或将它们嵌入到HTML文件中。 要捕获在网站中输入到特定表单的实际表单值，必须添加几行代码才能将表单值附加到日志请求中。

在表单的处理页面中，包括以下代码，将输入的表单值附加到请求数据（除了将提交的表单值写入外部数据库或其他位置之外）：

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

此过程将在[!DNL Form Processing]页的请求数据中附加定义的表单值。 在日志数据中，附加值将作为[!DNL Form Processing]页面的查询字符串可用，如下所示。 例如，v_1、v_2、v_3和v_4现在将是包含输入到相应表单字段中的查询的字符串。 您可以对要捕获的任何其他表单字段和值复制上述示例中描述的语法。

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您希望捕获每个表单字段和值并将其用于分析，可以使用以下语法：

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

此示例将采用HTML中存在的所有表单字段及其各自的值，并将它们作为查询字符串附加到[!DNL Form Processing]页面的日志条目中。 应当指出，这将包括表单中存在的任何隐藏字段。

日志数据将增强，详见下表：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与NAME查询字符串关联的值 | v_1=John Smith |
| v_2 | 与CITY查询字符串关联的值 | v_2=洛杉矶 |
| v_3 | 与STATE查询字符串关联的值 | v_3=California |
| v_4 | 与ZIP查询字符串关联的值 | v_4=90210 |
