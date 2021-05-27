---
description: 作为收集的基线测量数据的一部分，传感器在从Web服务器发出请求时会收集从访客计算机发送的域Cookie。
title: 通过 Cookie 获取测量数据
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# 通过 Cookie 获取测量数据{#acquiring-measurement-data-through-cookies}

作为收集的基线测量数据的一部分，传感器在从Web服务器发出请求时会收集从访客计算机发送的域Cookie。

这包括访客与系统交互时网站设置的永久性Cookie和会话Cookie。

在大多数情况下，网站会设置永久性Cookie以识别访客或捕获用户输入，以供在后续访客会话中使用。 可以捕获写入永久Cookie并将其存储在永久Cookie中的任何信息，并将其与Data Workbench Server中的所有其他测量数据一起使用。

此类永久Cookie的示例可能涉及客户标识符，其形式为驻留在访客计算机上的特定于域的Cookie中存在的数字键。 除了将用户识别为回访访客之外，还可以使用永久Cookie进一步将访客识别为回访客户，或将访客绑定到客户数据库中包含的信息，以允许离线客户人口统计信息显示在[!DNL Site]中并用于交互式分析。

会话Cookie是通过表单字段或网站中的其他动态交互元素收集用户输入的良好机制。 对于网站实施表单以捕获特定于用户的输入数据的情况，仅当会话处于活动状态时，该信息才会在会话Cookie中保留。 当用户离开您的网站或随后结束会话时，该信息将不再存储在用户的计算机上。 但是，输入的信息由[!DNL Sensor]捕获，并作为[!DNL Site]内的测量数据提供。

以下是使用会话Cookie捕获访客输入的单个表单变量的示例。

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

在此示例中，调用函数以在访客的计算机上设置会话Cookie，其中包含字段名称和在表单字段中输入的值。 提交表单并请求后续网页后，会话Cookie集将传递到Web服务器并由[!DNL Sensor]收集。 因此，Data Workbench Server中提供了以下数据以供数据分析使用：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与v_1 Cookie关联的值。 此值表示在表单字段中输入的导致设置会话Cookie的名称。 | v_1=John Smith |

还可以利用会话Cookie来迭代地捕获HTML页面中存在的表单字段或多个嵌入式JavaScript变量。 在以下示例中，JavaScript用于递归捕获HTML文件中存在的任何表单字段，并使用相应的名称=值对设置会话Cookie。

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

在此示例中，会在访客的计算机上设置会话Cookie，其名称和值包括表单中存在的每个表单字段。 这包括输入字段、复选框、单选按钮、选中框和文本区域。 正如您在本例中所注意到的，由于表单字段数未知，因此必须将所有表单名称和字段值捕获为一个字符串（以与号分隔）。 必须执行此步骤，因为用户在其计算机上的某个时间点可能拥有的Cookie数量存在限制。 Microsoft Internet Explorer在开始删除最早的会话Cookie之前，仅允许存在20个会话Cookie。
