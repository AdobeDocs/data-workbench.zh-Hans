---
description: 继承配置文件的转换数据集包含文件中含有与数据集构建的转换阶段相关的参数。
solution: Analytics
title: 转换数据集包含文件
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 转换数据集包含文件{#transformation-dataset-include-files}

继承配置文件的转换数据集包含文件中含有与数据集构建的转换阶段相关的参数。

文件的第一行定义了支持 Extended Dimensions（扩展维度）、Parameters（参数）、Reprocess（重新处理）、Stage（阶段）和 Transformations（转换）参数的 [!DNL TransformationInclude] 类型。其他所有参数都必须在数据集配置文件 Dataset 目录的 [!DNL Transformation.cfg] 文件中定义。

Including parameters other than Extended Dimensions, Parameters, Reprocess, Stage, and Transformations in a [!DNL Transformation Dataset Include] file generates errors.

You can name a [!DNL Transformation Dataset Include] file anything you want, but its file extension must be [!DNL .cfg]. 文件必须存储在&#x200B;*继承配置文件*\Dataset\Transformation 目录中。Because the files are loaded recursively during the transformation phase of dataset construction, you can store the [!DNL Transformation Dataset Include] files at any level within the directory (for example, *inherited profile name*\Dataset\Transformation\*folder name*\*include file name*.cfg).

>[!NOTE]
>
>文件中定义了许多特定于Web的站点配置 [!DNL Transformation Dataset Include] 参数。 有关这些参数的信息，请参 [阅Web数据的配置设置](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

The following table describes the parameters that are available in a [!DNL Transformation Dataset Include] file:

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Extended Dimensions（扩展维度） </td> 
   <td colname="col2"> 可选。定义扩展维度。请参阅 <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Extended Dimensions（扩展维度）</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参数 </td> 
   <td colname="col2"> 可选。您可以在其他配置参数中引用的变量。有关详细信息，请参阅<a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50">在数据集包含文件中定义参数</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess（重新处理） </td> 
   <td colname="col2"> <p>可选。此处可以输入任意字符或字符组合。更改此参数并保存文件会开始重新转换数据。 </p> <p> 有关重新处理数据的信息，请参阅<a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">重新处理和重新转换</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage（阶段） </td> 
   <td colname="col2"> <p>可选。应用于此<span class="wintitle">转换数据集包含</span>文件的处理阶段名称。处理阶段是在 <span class="filepath">Transformation.cfg</span> 文件的 Stages（阶段）参数中定义的。 </p> <p> <p>注意：当您指定阶段时，阶段的名称必须与数据集配置文件的 <span class="filepath">Transformation.cfg</span> 文件中 Stages（阶段）参数所列的名称完全匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations（转换） </td> 
   <td colname="col2"> 可选。定义需要在转换过程中应用的数据转换。有关可用转换类型的信息，请参阅<a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md">数据转换</a>。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有关文件中参数的说明，请 [!DNL Transformation.cfg] 参阅转换 [配置文件](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)。

You should keep the following points in mind whenever you are working with [!DNL Transformation Dataset Include] files:

* 更改此文件中的任何参数都需要重新转换数据。
* [!DNL CrossRows]、 [!DNL ODBCLookup]、 [!DNL Sessionize]和 [!DNL AppendURI] 转换仅在文件中定义时才 [!DNL Transformation Dataset Configuration] 有效。 有关这些转换的信息，请参阅数 [据转换](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

* 您可以将上述任何参数添加到 [!DNL Transformation Dataset Include] 文件中，只需在记事本中打开并编辑该文件即可。当您在 Data Workbench 中重新打开该文件时，系统便会显示您做出并保存的所有更改。在添加新参数时，使用空格键（而不是 Tab 键）可向上一个标题级别的右侧缩进两 (2) 个空格。

If you subscribe to Adobe&#39;s [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] data service, Adobe provides you with an internal profile consisting of a set of data transformations and extended dimensions that are created specifically for the data service. The transformations and dimensions are defined in [!DNL Transformation Dataset Include] files that are included in the Dataset directory of the internal profile. For instructions to install the internal profile for the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] data service, see the *Data Workbench User Guide*.
