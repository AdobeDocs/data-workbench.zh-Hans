---
description: 继承配置文件的转换数据集包含文件中含有与数据集构建的转换阶段相关的参数。
title: 转换数据集包含文件
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 59%

---

# 转换数据集包含文件{#transformation-dataset-include-files}

{{eol}}

继承配置文件的转换数据集包含文件中含有与数据集构建的转换阶段相关的参数。

文件的第一行定义了支持 Extended Dimensions（扩展维度）、Parameters（参数）、Reprocess（重新处理）、Stage（阶段）和 Transformations（转换）参数的 [!DNL TransformationInclude] 类型。其他所有参数都必须在数据集配置文件 Dataset 目录的 [!DNL Transformation.cfg] 文件中定义。

在 [!DNL Transformation Dataset Include] 文件会生成错误。

您可以将 [!DNL Transformation Dataset Include] 需要的任何文件，但其文件扩展名必须为 [!DNL .cfg]. 文件必须存储在&#x200B;*继承配置文件*\Dataset\Transformation 目录中。由于文件是在数据集构建的转换阶段递归加载的，因此您可以存储 [!DNL Transformation Dataset Include] 目录中任何级别的文件(例如， *继承配置文件名称*\Dataset\Transformation\*folder name*\*include file name*.cfg)。

>[!NOTE]
>
>Site的许多特定于Web的配置参数在 [!DNL Transformation Dataset Include] 文件。 有关这些参数的信息，请参阅 [Web数据的配置设置](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

下表介绍了 [!DNL Transformation Dataset Include] 文件：

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 扩展维度 </td> 
   <td colname="col2"> 可选。定义扩展维度。请参阅 <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 扩展维度</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参数 </td> 
   <td colname="col2"> 可选。您可以在其他配置参数中引用的变量。有关详细信息，请参阅 <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 在数据集包含文件中定义参数</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess（重新处理） </td> 
   <td colname="col2"> <p>可选。此处可以输入任意字符或字符组合。更改此参数并保存文件会开始重新转换数据。 </p> <p> 有关重新处理数据的信息，请参阅 <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新处理和重新转换</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage（阶段） </td> 
   <td colname="col2"> <p>可选。应用于此<span class="wintitle">转换数据集包含</span>文件的处理阶段名称。处理阶段是在 <span class="filepath">Transformation.cfg</span> 文件的 Stages（阶段）参数中定义的。 </p> <p> <p>注意：当您指定阶段时，阶段的名称必须与数据集配置文件的 <span class="filepath">Transformation.cfg</span> 文件中 Stages（阶段）参数所列的名称完全匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations（转换） </td> 
   <td colname="col2"> 可选。定义需要在转换过程中应用的数据转换。有关可用转换类型的信息，请参阅 <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 数据转换</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有关 [!DNL Transformation.cfg] 文件，请参阅 [转换配置文件](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

每当您使用 [!DNL Transformation Dataset Include] 文件：

* 更改此文件中的任何参数都需要重新转换数据。
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]和 [!DNL AppendURI] 转换仅在 [!DNL Transformation Dataset Configuration] 文件。 有关这些转换的信息，请参阅 [数据转换](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* 您可以将上述任何参数添加到 [!DNL Transformation Dataset Include] 文件中，只需在记事本中打开并编辑该文件即可。当您在 Data Workbench 中重新打开该文件时，系统便会显示您做出并保存的所有更改。在添加新参数时，使用空格键（而不是 Tab 键）可向上一个标题级别的右侧缩进两 (2) 个空格。

如果您订阅Adobe [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 数据服务中，“Adobe”为您提供了一个内部配置文件，其中包含一组专门为数据服务创建的数据转换和扩展维度。 转换和维度在 [!DNL Transformation Dataset Include] 包含在内部配置文件的Dataset目录中的文件。 有关为 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 数据服务，请参阅 *Data Workbench用户指南*.
