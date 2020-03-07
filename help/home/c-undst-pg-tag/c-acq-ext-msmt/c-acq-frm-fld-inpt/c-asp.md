---
description: 网页通常使用ASP(Active Server Pages)编程语言进行结构化。
solution: Analytics
title: ASP特定信息
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ASP特定信息{#asp-specific-information}

网页通常使用ASP(Active Server Pages)编程语言进行结构化。

ASP是一种在IIS(Internet Information Services)中运行的Microsoft技术。 当浏览器请求ASP文件时，IIS会将该请求传递给ASP引擎。 ASP引擎逐行读取ASP文件，并执行文件中的脚本。 最后，ASP文件作为纯HTML返回到浏览器。 ASP提供RESPONSE或REQUEST对象，除了其他用途外，还允许对用户查询或从HTML表单提交的数据进行响应或请求。

在某些情况下，您可能不希望将输入到表单中的值附加到用户浏览器地址栏中显示的URL或HTML代码本身中可查看的URL。 简单的服务器端JavaScript允许您在日志文件中附加表单字段名称及其各自的值，而无需在用户的浏览器中提供它们或将它们嵌入到HTML文件中。 要捕获在网站中特定表单中输入的实际表单值，必须添加几行代码才能将表单值附加到日志请求中。

在表单的处理页面中，包括以下代码，以将输入的表单值附加到请求数据（除了将提交的表单值写入外部数据库或其他位置之外）:

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

此过程会将定义的表单值附加到页面的请求数据 [!DNL Form Processing] 中。 在日志数据中，附加的值将作为页面的查询字符串 [!DNL Form Processing] 可用，如下图所示。 例如，v_1、v_2、v_3和v_4现在将是查询字符串，其中包含输入到相应表单字段中的数据。 您可以对要捕获的任何其他表单字段和值复制上述示例中描述的语法。

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您希望捕获每个表单字段和值并将其用于分析，则可以使用以下语法：

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

此示例将采用HTML中存在的所有表单字段及其各自的值，并将它们作为查询字符串附加到页面的日志条目 [!DNL Form Processing] 中。 应该指出，这将包括表单中存在的任何隐藏字段。

日志数据将增强，如下表所述：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与NAME查询字符串关联的值 | v_1=John Smith |
| v_2 | 与CITY查询字符串关联的值 | v_2=洛杉矶 |
| v_3 | 与STATE查询字符串关联的值 | v_3=加利福尼亚 |
| v_4 | 与ZIP查询字符串关联的值 | v_4=90210 |

