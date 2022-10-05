---
description: 传感器在服务器上使用时，可以从任何有效的HTTP请求或响应标头或可通过服务器API访问的变量中收集事件数据字段。
title: 可扩展字段
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---

# 可扩展字段{#extensible-fields}

{{eol}}

传感器在服务器上使用时，可以从任何有效的HTTP请求或响应标头或可通过服务器API访问的变量中收集事件数据字段。

要收集此类数据字段，您必须在 [!DNL txlogd.conf] 配置文件 [!DNL Sensor].

* [请求标头](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [服务器变量](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## 请求标头 {#section-22766692b45546d8bfc93dbe3bc9368f}

以下是用于指定要在 [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

收集的数据由 [!DNL Sensor] 到 [!DNL .vsl] 由创建的文件 [!DNL data workbench server]. 例如，要从请求标头“Host”中收集特定请求标头值，您需要在 [!DNL txlogd.conf]. 数据将记录到事件数据记录中的字段“cs(Host)”。

## 服务器变量 {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] 可以使用“特殊日志字段”条目(包含在 [!DNL txlogd.conf] 文件。 除或之外，您还可以使用“SpecialLogField”条目来收集请求标头，而不是使用“LogHeader”条目。 请参阅 [请求标头](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). 请求标头选项仍可用于进行向后兼容性。

以下是用于在 [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

下表包含“SpecialLogField”条目的组件描述。

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
   <td colname="col2"> 在事件数据记录中将收集数据记录到的字段的名称，以及 <span class="filepath"> .vsl </span> 由创建的文件 <span class="keyword"> data workbench server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>可用于 <span class="wintitle"> 传感器 </span> 通过服务器的API </p> <p>示例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_log或vys_cookie </p> <p>指定阶段要求您知道哪些服务器变量可用于vys_log和vys_cookie。 </p> <p>示例：对于serverVariable response.p3p，您应输入vys_log。 </p> </td> 
  </tr> 
 </tbody> 
</table>

有关配置帮助 [!DNL Sensor] 要收集可扩展的事件数据记录字段，请联系Adobe咨询服务。
