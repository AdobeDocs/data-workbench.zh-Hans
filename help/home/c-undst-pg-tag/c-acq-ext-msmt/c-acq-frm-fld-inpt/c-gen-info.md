---
description: 在网页中输入到表单中的值可以通过使用JavaScript收集并附加到随后请求的页面（在表单提交时）的查询字符串中。
solution: Analytics
title: 一般信息
topic: Data workbench
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 一般信息{#general-information}

在网页中输入到表单中的值可以通过使用JavaScript收集并附加到随后请求的页面（在表单提交时）的查询字符串中。

如下例所示。 在HTML页面中使用的任何表单验证脚本之后加入此JavaScript。

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

此示例将浏览器用户在表单中输入的值附加到在“表单操作”值中指示的后续“thankyou.asp”页面，如下所示：

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

除了由收集的基线测量值外，还将利用此请求获得以下扩展测量值 [!DNL Sensor]:

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与NAME表单字段关联的值 | v_1=John Smith |
| v_2 | 与CITY表单字段关联的值 | v_2=洛杉矶 |
| v_3 | 与STATE表单字段关联的值 | v_3=加利福尼亚 |
| v_4 | 与ZIP表单字段关联的值 | v_4=90210 |

