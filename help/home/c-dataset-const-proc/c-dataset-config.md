---
description: 数据集配置是指编辑配置文件（其参数为数据集构建提供规则）的过程。
solution: Analytics
title: 了解数据集配置
topic: Data workbench
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 了解数据集配置{#understanding-dataset-configuration}

数据集配置是指编辑配置文件（其参数为数据集构建提供规则）的过程。

构建的数据集实际位于 Data Workbench Server 计算机上存储的 [!DNL temp.db] 文件中，而数据集的配置文件则位于配置文件的目录内。配置文件包含一组出于特定分析目的而构建数据集（包括其扩展维度）的配置文件。此外，配置文件还包含一些实体（例如量度、派生维度、工作区、报表和可视化）的定义，以使分析人员能够与数据集交互并从中获取信息。

您正在编辑其数据集配置文件的配置文件就是您的数据集配置文件。数据集配置文件可以引用多个继承配置文件（可以是您创建和维护的任意配置文件），以便您能够完全根据自己的分析需要对 Adobe 应用程序进行配置。数据集配置文件还可以引用随 Adobe 应用程序一起提供的内部配置文件，为应用程序中所有可用的功能提供基础。

有关随 Adobe 应用程序一起提供的各类配置文件的详细信息，请参阅《Data Workbench 用户指南》**。

<!--
c_req_config_files.xml
-->

任何 Adobe 应用程序的数据集配置文件都必须在 Insight Server 计算机上包含以下配置文件：

* **Profile.cfg：**&#x200B;列出继承配置文件和配置文件的处理服务器。处理服务器是用于处理配置文件数据的 Insight Server DPU。如果您安装了 Insight Server 群集，则可以指定多台 Insight Server 计算机来运行单个配置文件。

   有关将继承配置文件添加到数据集配置文件 [!DNL Profile.cfg] 文件的说明，请参阅《服务器产品安装和管理指南》**。有关安装 Insight Server 群集或将数据集配置文件配置为在 Insight Server 群集上运行的信息，请参阅《服务器产品安装和管理指南》**。

* **Dataset\Log Processing.cfg：**&#x200B;控制数据集构建过程中的日志处理阶段。请参阅 [日志处理](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061)。 有关该文件的详细信 [!DNL Log Processing.cfg] 息，请参阅 [日志处理配置文件](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。

* **Dataset\Transformation.cfg：**&#x200B;控制数据集构建过程中的转换阶段。请参阅 [转换](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). [!DNL Transformation.cfg] 文件通常配置数据集以进行特定于配置文件的分析。有关该文件的详细信 [!DNL Transformation.cfg] 息，请参阅 [转换配置文件](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)。

* **数据集包含文件：** 文 [!DNL dataset include] 件包含数据集配置文件或文件中包含的参数子集， [!DNL Log Processing.cfg] 但 [!DNL Transformation.cfg] 是在继承的配置文件中存储和管理。 [!DNL Dataset include] 文件是主数据集配置文件的补充。 有关详细信息，请参阅 [数据集包含文件](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

The dataset profile provided to you during the implementation of your Adobe application contains a set of dataset configuration files that you can open, edit, and save using the [!DNL Profile Manager].

For information about the [!DNL Profile Manager], see the *Insight User Guide*.

<!--
c_addl_config_files.xml
-->

以下文件可让您控制数据集构建过程的其他方面（尽管并非所有数据集都需要）：

* **：**[!DNL Log Processing Mode.cfg]Log Processing Mode.cfg 文件可让您暂停将数据处理到数据集中、指定离线源或指定 Data Workbench Server 保存其状态文件的频率。See [Additional Configuration Files](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **：**[!DNL Server.cfg]Server.cfg 文件为连接到 Data Workbench Server 的 Data Workbench 计算机指定默认数据缓存大小（以字节为单位）。See [Additional Configuration Files](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg 和 Transform Mode.cfg：**&#x200B;仅当您获得在 Adobe 应用程序中使用数据转换功能的许可时，这些文件才可用。[!DNL Transform.cfg] 文件包含为转换功能定义日志源和数据转换的参数。您定义的转换可处理源数据，并将其输出为您指定的格式。[!DNL Insight Transform Mode.cfg] 文件可让您暂停将数据处理到数据集中、指定离线源或指定运行转换功能的 Insight Server 保存其状态文件的频率。请参阅 [转换功能](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)。

<!--
c_next_steps.xml
-->

有关特定数据集配置任务的信息，请使用下表找到并阅读您感兴趣的任务：

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 如果您想要... </th> 
   <th colname="col2" class="entry"> 请参阅... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>定义日志源 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Log Sources（日志源） </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>确定哪些日志条目会在日志处理过程中进入数据集 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 数据过滤器</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 日志条目条件</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>对具有大量事件数据的跟踪 ID 启用拆分功能 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> 键拆分</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>配置 Insight Server 以作为文件服务器单元运行 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 配置 Insight Server 文件服务器单元 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>配置 Insight Server 以作为集中标准化服务器运行 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 配置 Insight Server 文件服务器单元 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>设置时区以用于创建时间维度和进行时间转换 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 时区 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>对 Adobe 提供的内部配置文件所包含的数据集配置文件做出细微更改 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> 编辑现有数据集包含文件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>指定要从日志处理过程传递到转换过程的新数据字段 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 创建新数据集包含文件 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> 日志处理数据集包含文件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>定义转换 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 数据转换 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 创建新数据集包含文件 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 转换数据集包含文件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>创建扩展维度 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Extended Dimensions（扩展维度） </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 创建新数据集包含文件 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 转换数据集包含文件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>定义要在日志处理过程或转换过程使用的参数 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 在数据集包含文件中定义参数 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>了解可供监控或管理数据集的 Insight 界面 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> 使用数据集配置界面 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>隐藏某些扩展维度以使其不会显示在 Insight 的维度菜单中 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> 隐藏数据集组件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>覆盖配置文件中某些您无法或不想修改的数据集配置文件 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> 隐藏数据集组件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新处理您的数据集 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新处理和重新转换 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

