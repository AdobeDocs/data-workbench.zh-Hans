---
description: 数据集包含文件提供了一种灵活的方式来配置您的数据集。
solution: Analytics
title: 处理数据集包含文件
topic: Data workbench
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 处理数据集包含文件{#working-with-dataset-include-files}

数据集包含文件提供了一种灵活的方式来配置您的数据集。

在每个文件内，您可以根据需要定义任意数量的字段、转换或维度，还可以基于包含文件所属的继承配置文件整理包含文件。在配置数据集时，您可以选择编辑随 Adobe 应用程序的内部配置文件一起提供的数据集包含文件，也可以为您创建的任何继承配置文件新建数据集包含文件。

当编辑内部配置文件的数据集包含文件的参数，并将更新的文件保存至数据集配置文件或创建的继承配置文件时，您实际上覆盖了文件的原始设置。只要您需要对数据集的内容做出细小更改（例如更改一个 Condition（条件）参数或参数的默认设置），Adobe 建议编辑内部配置文件的数据集包含文件。请参阅 [编辑现有数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). 但是，当您希望指定要从日志处理传递到转换的新字段、使用转换更新或创建新字段或定义扩展维时，最好创建新的数据集包含文件。 See [Creating New Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). 只要您认为合适，就可以对自己创建的文件进行编辑。
