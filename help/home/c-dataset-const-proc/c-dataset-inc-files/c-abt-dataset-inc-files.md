---
description: 随 Adobe 应用程序一起收到的许多内部配置文件都带有其自身的数据集配置文件。
title: 关于数据集包含文件
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 82%

---

# 关于数据集包含文件{#about-dataset-include-files}

{{eol}}

随 Adobe 应用程序一起收到的许多内部配置文件都带有其自身的数据集配置文件。

由于内部配置文件是数据集配置文件的子配置文件，因此其数据集配置文件中包含的规则可以为数据集构建的日志处理阶段或转换阶段提供附加参数。内部配置文件和您创建的任何继承配置文件的数据集配置文件称为数据集包含文件。

数据集包含文件中含有数据集配置文件的主数据集配置文件（[!DNL Log Processing.cfg] 或 [!DNL Transformation.cfg]）中包含的部分参数。将调用包含与日志处理相关参数的数据集包含文件 [!DNL Log Processing Dataset Include] 文件(请参阅 [日志处理数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab))，而与转换关联的数据集包含文件则被调用 [!DNL Transformation Dataset Include] 文件。 请参阅 [转换数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). 您可以创建多个数据集包含文件以用在数据集构建过程中。完整的数据集包括在数据集配置文件及任何继承配置文件的所有数据集配置文件中定义的所有字段、转换和扩展维度。
