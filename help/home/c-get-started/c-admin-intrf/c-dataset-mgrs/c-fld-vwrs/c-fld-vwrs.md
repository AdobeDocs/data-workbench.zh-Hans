---
description: 字段查看器是一个包含一个或多个数据字段值的表。
solution: Analytics
title: 字段查看器
topic: Data workbench
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 字段查看器{#field-viewer}

字段查看器是一个包含一个或多个数据字段值的表。

显示值的这些字段包括数据集日志源、转换或扩展维度的输入或输出。字段的名称显示在列标题中，并且每一行包含一行源数据的字段值。Because field viewers enable you to see a field’s values, they are helpful in writing and testing [regular expressions](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

You can open a field viewer as a callout from a [!DNL Transformation Dependency] map or as a standalone visualization from the [!DNL Admin] menu:

* Creating a field viewer from a [!DNL Transformation Dependency] map. When you open a field viewer from a [!DNL Transformation Dependency] map, the viewer is populated automatically based on the log source, transformation, or dimension that you right-click. 对于日志源或转换，查看器中的字段是该日志源或转换的输入或输出。对于维度，字段是该维度的输入。您可以根据需要添加或删除字段。

* 创建作为独立可视化的字段查看器。当您以独立可视化形式打开字段查看器时，可以创建或 [!DNL Log Processing Field Viewer] 字段查看器 [!DNL Transformation Field Viewer]。 查看器为空，您必须向查看器添加所需的字段。对于文 [!DNL Log Processing Field Viewer]件，您可以添加文件或任 [!DNL Log Processing.cfg] 何文件中的 [!DNL Log Processing Dataset Include] 字段。 对于文 [!DNL Transformation Field Viewer]件，您可以添加文件或任 [!DNL Transformation.cfg] 何文件中的 [!DNL Transformation Dataset Include] 字段。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>字段查看器不是表可视化；因此，它们没有与表关联的属性。

有关添加和删除字段以及在字段查看器中进行筛选的信息，请参阅管 [理界面](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)。
