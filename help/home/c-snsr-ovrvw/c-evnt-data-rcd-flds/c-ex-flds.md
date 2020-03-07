---
description: 传感器在服务器上使用时，可以通过服务器的API从任何有效的HTTP请求或响应头或可用的变量收集事件数据的字段。
solution: Insight
title: 可扩展字段
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 可扩展字段{#extensible-fields}

传感器在服务器上使用时，可以通过服务器的API从任何有效的HTTP请求或响应头或可用的变量收集事件数据的字段。

To collect such fields of data, you must specify the desired header fields or variables in the [!DNL txlogd.conf] configuration file for [!DNL Sensor].

* [请求标题](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [服务器变量](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## 请求标题 {#section-22766692b45546d8bfc93dbe3bc9368f}

以下是在中指定要收集的请求标头字段（例如，“主机”、“接受编码”、“保持活动”等）的语法 [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

收集的数据将记 [!DNL Sensor] 录到由创建的文件中名为“cs(RequestHeaderName)” [!DNL .vsl] 的字段中 [!DNL data workbench server]。 例如，要从请求标题“Host”中收集特定请求标题值，您应在中键入“LogHeader Host” [!DNL txlogd.conf]。 数据记录到事件数据记录中的字段“cs(Host)”。

## 服务器变量 {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] 可以使用包含在文件中的SpecialLogField条目从响应标题或API可访问的服务器变量收集数据字 [!DNL txlogd.conf] 段。 除了“LogHeader”条目以外，您还可以使用“SpecialLogField”条目来收集请求标头。 请参阅 [请求标题](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)。 请求标题选项保持可向后兼容。

以下是用于在中指定“SpecialLogField”的语法 [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

下表包括“SpecialLogField”条目的组件描述。

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 组件 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(log field) </td> 
   <td colname="col2"> 在事件数据记录中记录收集数据的字段的名称以及由Data Workbench Server创建的 <span class="filepath"> .vsl </span> 文件 <span class="keyword"> 的名称 </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>传感器通过服务器的API可 <span class="wintitle"> 用 </span> 的任何服务器变量 </p> <p>示例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 阶段 </td> 
   <td colname="col2"> <p>vys_log或vys_cookie </p> <p>指定舞台要求您了解vys_log和vys_cookie可用的服务器变量。 </p> <p>示例：对于serverVariable response.p3p，您应输入vys_log。 </p> </td> 
  </tr> 
 </tbody> 
</table>

有关配置以收 [!DNL Sensor] 集可扩展的活动数据记录字段的帮助，请与Adobe咨询服务部门联系。
