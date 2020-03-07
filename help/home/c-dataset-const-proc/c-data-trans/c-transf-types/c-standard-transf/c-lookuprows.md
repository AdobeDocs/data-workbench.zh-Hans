---
description: LookupRows 转换查看具有相同跟踪 ID 的其他日志条目，并将输出字段的值设为输入行中指定字段的值。
solution: Analytics
title: LookupRows
topic: Data workbench
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# LookupRows{#lookuprows}

LookupRows 转换查看具有相同跟踪 ID 的其他日志条目，并将输出字段的值设为输入行中指定字段的值。

Because the [!DNL LookupRows] transformation performs its lookup on log entries and not lookup files, it is very similar to the [!DNL CrossRows] transformation. 请参 [阅CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)。

若要使用 [!DNL LookupRows] 转换，数据必须按时间排序并按源数据中的跟踪 ID 分组。因此， [!DNL LookupRows] 仅当在文件或文件中定 [!DNL Transformation.cfg] 义时才可 [!DNL Transformation Dataset Include] 用。

在查看下表中的参数描述时，请切记以下事项：

* 输出行是转换在给定的时间点处理的数据行。
* 输入行是其输入字段值用作转换输入的其他所有数据行（输出行之前、之后或包括输出行）。

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comments（备注） </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition（条件） </td> 
   <td colname="col2"> 将转换输出限制到特定的日志条目。如果某个特定日志条目不满足条件，Output Row Value Output（输出行值输出）参数中的字段将保持不变。输入仍可用于影响其他日志条目。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Condition（输入条件） </td> 
   <td colname="col2">仅从特定输入行接受转换的输入。如果某个特定<span class="wintitle">输入</span>行不满足输入条件，则将忽略来自该行的输入字段且不会影响其他输出行。但是仍将根据指定的条件修改来自该行的输出字段。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Row Key Input（输入行键输入） </td> 
   <td colname="col2"> 用作输入行的键的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Row Value Input（输入行值输入） </td> 
   <td colname="col2"> 输入行中字段的名称，在满足所有条件时该字段的值将复制到 Output Row Value Output（输出行值输出）参数中的字段。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operation（运算） </td> 
   <td colname="col2"> <p>对于每个输出行，应用于所有满足 <span class="wintitle">Input</span> Condition（输入条件）和 Input Row Key Input（输入行键输入）参数定义的全部条件的输入行以生成输出的运算： 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST 从数据中第一个匹配输入行（不是输出行之后的第一个匹配行）输出 Input Row Value Input（输入行值输入）参数中的字段值。 </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST 从数据中最后一个输入行（不是输出行之前的最后一个匹配行）输出 Input Row Value Input（输入行值输入）参数中的字段值。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Row Key Input（输出行键输入） </td> 
   <td colname="col2"> 用作输出行的键的字段名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Row Value Output（输出行值输出） </td> 
   <td colname="col2">输出行中字段的名称，在满足所有条件时从 Input Row Value Input（输入行值输入）参数的字段中复制该字段的值。具有相同 x-trackingid 和<span class="wintitle">输出行键输入</span>值的所有输出行将具有相同的<span class="wintitle">输出行值输出</span>值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Input Row Key Input（输入行键输入）、Input Row Value Input（输入行值输入）和 Input Condition（输入条件）参数共同定义每个跟踪 ID 的对照文件，而 Output Row Key Input（输出行键输入）、Output Row Value Input（输出行值输入）和 Condition（条件）参数控制文件中的对照内容和 Output Row Value Output（输出行值输出）指定的字段中存储的值。

为了更好地理解此转换的运算，请记住以下要点：

* 对于满足“条件”且具有非空“输出行键输入”的每个输出行：

   * 查找满足以下条件的 FIRST 或 LAST 输入行：

      * 输入行满足“输入条件”，并且
      * 输入行的 x-trackingid 等于输出行的 x-trackingid，并且
      * 输入行的“输入行键输入”等于输出行的“输出行键输入”

* 将输出行的“输出行值输出”设为输入行的“输入行值输入”。

注意事项 [!DNL LookupRows]

* 空键值不匹配任何内容。即使有带空键和非空值的输入行与匹配 [!DNL Input Condition], [!DNL Output Row Key Input] “”的输入行将始终生成 [!DNL Output Row Value Output] “”。

* 如果行的值和 [!DNL Input Condition]值相同，则行可能会自 [!DNL Input Row Key Input] 己 [!DNL Output Row Key Input] 查找。

如果有多个键值，则可以在应用转换之前使用转 [!DNL Format] 换(请参阅 [格式](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b))来组合 [!DNL LookupRows] 它们。

假定您的网站有一个“宠物登记”页，其中输入了名称和品种，而随后的“购买玩具”页仅使用宠物的名称。您希望将宠物名称与登记页上输入的宠物品种链接在一起。为此，您可以创建以下 [!DNL LookupRows] 转换：

![](assets/cfg_TransformationType_LookupRows.png)

我们使用前面所述的要点分析此示例：

* 对于 cs-uri-query(petname) 具有非空值的每个输出行：

   * 查找满足以下条件的 LAST 输入行：

      * 输入行包含具有非空值的 cs-uri-query(petbreed)，并且
      * 输入行的 x-trackingid 等于输出行的 x-trackingid，并且
      * 输入行的 cs-uri-query(petname) 值等于输出行的 cs-uri-query(petname) 值

* 将输出行的 x-pet-breed 值设为输入行的 cs-uri-query(petbreed) 值。

[!DNL LookupRows] 转换使用宠物名称（键）确保宠物品种同时链接到“宠物登记”和“购买玩具”页，这样您便可以分析为每种宠物购买的玩具，即使访客拥有多种宠物也可进行分析。
