---
description: 字段查看器是一个包含一个或多个数据字段值的表。
title: 字段查看器
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 48%

---

# 字段查看器{#field-viewer}

字段查看器是一个包含一个或多个数据字段值的表。

显示值的这些字段包括数据集日志源、转换或扩展维度的输入或输出。字段的名称显示在列标题中，并且每一行包含一行源数据的字段值。由于字段查看器允许您查看字段的值，因此编写和测试[正则表达式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)时，这些值非常有用。

您可以从[!DNL Transformation Dependency]映射中以标注形式打开字段查看器，或从[!DNL Admin]菜单以独立可视化形式打开字段查看器：

* 从[!DNL Transformation Dependency]映射创建字段查看器。 从[!DNL Transformation Dependency]映射中打开字段查看器时，查看器会根据您右键单击的日志源、转换或维度自动填充。 对于日志源或转换，查看器中的字段是该日志源或转换的输入或输出。对于维度，字段是该维度的输入。您可以根据需要添加或删除字段。

* 创建作为独立可视化的字段查看器。在作为独立可视化打开字段查看器时，可以创建[!DNL Log Processing Field Viewer]或[!DNL Transformation Field Viewer]。 查看器为空，您必须向查看器添加所需的字段。对于[!DNL Log Processing Field Viewer]，可以添加[!DNL Log Processing.cfg]文件或任何[!DNL Log Processing Dataset Include]文件中的字段。 对于[!DNL Transformation Field Viewer]，可以添加[!DNL Transformation.cfg]文件或任何[!DNL Transformation Dataset Include]文件中的字段。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>字段查看器不是表格可视化；因此，它们没有与表关联的属性。

有关在字段查看器中添加和删除字段以及进行筛选的信息，请参阅[管理界面](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)。
