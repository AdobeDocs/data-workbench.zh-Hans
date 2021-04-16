---
description: 作为收集的基线测量数据的一部分，传感器在从Web服务器发出请求时收集从访客机器发送的域Cookie。
title: 通过 Cookie 获取测量数据
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# 通过 Cookie 获取测量数据{#acquiring-measurement-data-through-cookies}

作为收集的基线测量数据的一部分，传感器在从Web服务器发出请求时收集从访客机器发送的域Cookie。

这包括当访客与您的系统交互时您的网站设置的永久和会话Cookie。

在大多数情况下，网站会设置永久Cookie来识别访客或捕获用户输入以在后续访客会话中使用。 写入并存储在永久Cookie中的任何信息都可以捕获并与Data Workbench Server中的所有其他测量数据一起使用。

此类永久Cookie的示例可能包括以数字键形式存在的客户标识符，该数字键存在于驻留在访客机器上的域特定Cookie中。 除了将用户标识为返回访客之外，持久Cookie还可用于进一步将访客标识为返回客户，或将访客绑定到客户数据库中包含的信息，以允许离线客户人口统计信息显示在[!DNL Site]中并用于交互分析。

会话Cookie是通过表单域或网站中的其他动态交互元素收集用户输入的良好机制。 如果某个网站实施表单以捕获特定于用户的输入数据，则只有会话处于活动状态时，该信息才会保留在会话Cookie中。 当用户离开您的网站或随后结束会话时，该信息不再存储在用户的计算机上。 但是，输入的信息由[!DNL Sensor]捕获，并作为[!DNL Site]中的测量数据提供。

以下是使用会话Cookie捕获由访客输入的单个表单变量的示例。

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

在此示例中，将调用一个函数，以在访客的计算机上设置一个会话Cookie，其中包含字段名称和在表单字段中输入的值。 提交表单并请求后续网页时，会话Cookie集会传递到Web服务器并由[!DNL Sensor]收集。 因此，Data Workbench Server中提供以下数据以用于数据分析:

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与v_1 cookie关联的值。 此值表示在表单字段中输入的NAME，该NAME导致设置会话Cookie。 | v_1=John Smith |

还可以利用会话cookie来迭代地捕获表单字段或HTML页中存在的多个嵌入的JavaScript变量。 在以下示例中，JavaScript用于递归捕获HTML文件中存在的任何表单字段，并设置具有相应名称=值对的会话Cookie。

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

在此示例中，会在访客的计算机上设置会话Cookie，其名称和值包含表单中存在的每个表单字段。 这包括输入字段、复选框、单选按钮、选中框和文本区域。 正如您在此示例中所注意到的，由于表单字段的数量未知，因此必须将所有表单名称和字段值捕获为一个字符串，并用&amp;符分隔。 必须执行此步骤，因为用户在某个时间点在其计算机上可能拥有的Cookie数量有限。 Microsoft Internet Explorer在开始删除最旧的会话Cookie之前，只允许存在二十(20)个会话Cookie。
