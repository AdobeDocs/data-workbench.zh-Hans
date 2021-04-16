---
description: 传感器在服务器上使用时，可以从任何有效的HTTP请求或响应头或可通过服务器的API访问的变量中收集事件数据字段。
title: 可扩展字段
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# 可扩展字段{#extensible-fields}

传感器在服务器上使用时，可以从任何有效的HTTP请求或响应头或可通过服务器的API访问的变量中收集事件数据字段。

要收集此类数据字段，必须在[!DNL Sensor]的[!DNL txlogd.conf]配置文件中指定所需的标题字段或变量。

* [请求标头](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [服务器变量](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## 请求标头{#section-22766692b45546d8bfc93dbe3bc9368f}

以下是在[!DNL txlogd.conf]中指定要收集的请求标头字段（例如，“主机”、“接受编码”、“保持活动”等）的语法：

```
LogHeader RequestHeaderName
```

收集的数据由[!DNL Sensor]记录到由[!DNL data workbench server]创建的[!DNL .vsl]文件中名为“cs(RequestHeaderName)”的字段。 例如，要从请求标头“Host”中收集特定请求标头值，应在[!DNL txlogd.conf]中键入“LogHeader Host”。 数据将记录到事件数据记录中的字段“cs(Host)”。

## 服务器变量{#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] 可以使用包含在文件中的SpecialLogField条目从响应头或API可访问的服务器变量收集数据 [!DNL txlogd.conf] 字段。除“LogHeader”条目之外，您还可以使用“SpecialLogField”条目来收集请求标头。 请参阅[请求标头](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)。 请求标头选项仍可用于向后兼容。

以下是用于在[!DNL txlogd.conf]中指定“SpecialLogField”的语法：

```
SpecialLogField cs(log field) = serverVariable stage
```

下表包括“SpecialLogField”条目的组件说明。

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
   <td colname="col2"> 在事件数据记录中记录所收集数据的字段的名称，以及由<span class="keyword"> Data Workbench Server </span>创建的<span class="filepath"> .vsl </span>文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>通过服务器的API可用于<span class="wintitle">传感器</span>的任何服务器变量 </p> <p>示例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 阶段 </td> 
   <td colname="col2"> <p>vys_log或vys_cookie </p> <p>指定舞台需要您知道vys_log和vys_cookie有哪些服务器变量。 </p> <p>示例：对于serverVariable response.p3p，您将输入vys_log。 </p> </td> 
  </tr> 
 </tbody> 
</table>

有关配置[!DNL Sensor]以收集可扩展事件数据记录字段的帮助，请与Adobe咨询服务部门联系。
