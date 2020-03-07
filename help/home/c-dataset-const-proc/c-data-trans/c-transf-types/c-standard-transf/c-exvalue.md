---
description: 如果您在处理 Web 数据，则可以使用 ExtractValue 转换从查询字符串、cookie 或网站数据中具有类似编码的字段提取值。
solution: Analytics
title: ExtractValue
topic: Data workbench
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExtractValue{#extractvalue}

如果您在处理 Web 数据，则可以使用 ExtractValue 转换从查询字符串、cookie 或网站数据中具有类似编码的字段提取值。

请注意，要提取的值所对应的名称在每个日志条目中可能有所不同。

<table id="table_D16A39BE035043628A4D6F7452952304"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 转换的描述性名称。可以在此处输入任何名称。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comments（备注） </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition（条件） </td> 
   <td colname="col2"> 应用此转换的条件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Name（输入名称） </td> 
   <td colname="col2"> <p>要从 Input Query（输入查询）中提取的字段名称。 </p> <p> <p>注意：如果 Input Name（输入名称）是一个矢量（即，显示多个名称），则仅提取一个值。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Query（输入查询） </td> 
   <td colname="col2"> 从中提取值的编码映射（查询字符串、cookie 等）。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Value（输出值） </td> 
   <td colname="col2"> 用于捕获提取的解码值的字段名称。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

如果您希望提取搜索短语，则可以提取整个短语，如果需要，还可以使用 [!DNL Tokenize] 转换将短语拆分为搜索词。有关转换的信 [!DNL Tokenize] 息，请参 [阅Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c)。

此示例配置一个 [!DNL ExtractValue] 转换，用于从 cs(referrer-query) 提取 x-v-search-querynames 字段的值，并将它们存储在 x-search-phrase 字段中。

![](assets/cfg_TransformationType_ExtractValue.png)

