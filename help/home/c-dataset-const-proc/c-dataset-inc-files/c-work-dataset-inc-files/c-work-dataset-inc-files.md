---
description: 数据集包含文件提供了一种灵活的方式来配置您的数据集。
title: 处理数据集包含文件
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 81%

---

# 处理数据集包含文件{#working-with-dataset-include-files}

{{eol}}

数据集包含文件提供了一种灵活的方式来配置您的数据集。

在每个文件内，您可以根据需要定义任意数量的字段、转换或维度，还可以基于包含文件所属的继承配置文件整理包含文件。在配置数据集时，您可以选择编辑随 Adobe 应用程序的内部配置文件一起提供的数据集包含文件，也可以为您创建的任何继承配置文件新建数据集包含文件。

当编辑内部配置文件的数据集包含文件的参数，并将更新的文件保存至数据集配置文件或创建的继承配置文件时，您实际上覆盖了文件的原始设置。只要您需要对数据集的内容做出细小更改（例如更改一个 Condition（条件）参数或参数的默认设置），Adobe 建议编辑内部配置文件的数据集包含文件。请参阅 [编辑现有数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). 但是，如果要指定要从日志处理传递到转换的新字段、使用转换更新或创建新字段，或定义扩展维度，则最好创建新数据集包含文件。 请参阅 [创建新数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). 只要您认为合适，就可以对自己创建的文件进行编辑。
