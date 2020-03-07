---
description: 作为所收集的基线测量数据的一部分，传感器在从Web服务器发出请求时会收集从访客机器发送的域cookie。
solution: Analytics
title: 通过Cookie获取测量数据
topic: Data workbench
uuid: 34cd6baf-6317-4774-8165-58208698b53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 通过Cookie获取测量数据{#acquiring-measurement-data-through-cookies}

作为所收集的基线测量数据的一部分，传感器在从Web服务器发出请求时会收集从访客机器发送的域cookie。

这包括访客与系统交互时网站设置的永久和会话Cookie。

在大多数情况下，网站会设置永久cookies来识别访客或捕获用户输入，以便在后续访客会话中使用。 写入永久Cookie并存储在永久Cookie中的任何信息都可以捕获并与Data Workbench Server内的所有其他测量数据一起使用。

此类永久cookie的示例可能涉及以数字密钥形式存在的客户标识符，该数字密钥存在于驻留在访客计算机上的域特定cookie中。 除了将用户识别为回访访客外，永久cookie还可用于进一步将访客识别为回访客户或将访客绑定到客户数据库中包含的信息，以允许离线客户人口统计信息显示在内部并用于交互 [!DNL Site] 式分析。

会话Cookie可以是收集用户通过表单字段或网站中其他动态交互式元素输入的良好机制。 如果网站实施表单以捕获用户特定的输入数据，则只有会话处于活动状态时，该信息才会保留在会话Cookie中。 当用户离开您的网站或随后结束会话时，该信息不再存储在用户的计算机上。 但是，输入的信息由中的测量数 [!DNL Sensor] 据捕获并可用作测量数据 [!DNL Site]。

以下是使用会话cookie捕获访客输入的单个表单变量的示例。

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

在此示例中，调用函数在访客的计算机上设置一个会话cookie，其中包含字段名称和在表单字段中输入的值。 在提交表单并请求后续网页时，会话Cookie集会传递到Web服务器并由收集 [!DNL Sensor]。 因此，Data Workbench Server中提供了以下数据以用于数据分析：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与v_1 cookie关联的值。 此值表示在表单字段中输入的NAME，该字段导致设置会话Cookie。 | v_1=John Smith |

会话cookie还可用于迭代地捕获HTML页面内存在的表单字段或多个嵌入的JavaScript变量。 在以下示例中，JavaScript用于递归捕获HTML文件中存在的任何表单字段，并使用相应的name=value对设置会话Cookie。

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

在此示例中，会在访客的计算机上设置会话Cookie，其中包含表单中存在的每个表单字段的名称和值。 这包括输入字段、复选框、单选按钮、选中框和文本区域。 正如您在本例中所注意到的，由于表单字段的数量未知，因此必须将所有表单名称和字段值捕获为单个字符串，并用&amp;符分隔。 必须执行此步骤，因为用户在某个时间点在其计算机上可能拥有的cookie数量有限。 Microsoft Internet Explorer仅允许在删除最旧的Cookie之前存在二十(20)个会话Cookie。
