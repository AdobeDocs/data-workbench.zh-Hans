---
description: 您可以从依赖关系图中作为标注打开字段查看器，也可以从“管理员”菜单中作为独立可视化打开字段查看器。
title: 创建字段查看器
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 63%

---

# 创建字段查看器{#create-a-field-viewer}

{{eol}}

您可以从依赖关系图中作为标注打开字段查看器，也可以从“管理员”菜单中作为独立可视化打开字段查看器。

## 从依赖关系图创建字段查看器 {#section-040cb83c902b49c48b841d35abc127e5}

从依赖关系图打开字段查看器时(如 [打开字段查看器](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27))，则查看器会根据您右键单击的日志源、转换或维度自动填充。 对于日志源或转换，查看器中的字段是该日志源或转换的输入或输出。对于维度，字段是该维度的输入。您可以根据需要添加或删除字段。

## 创建字段查看器作为独立可视化 {#section-11d10e46631d4fdca45d7534336e1e80}

当您作为独立可视化打开字段查看器时，可以创建 [!DNL Log Processing Field Viewer] 或 [!DNL Transformation Field Viewer]. 查看器为空，您必须向查看器添加所需的字段。对于 [!DNL Log Processing Field Viewer]，则可以添加 [!DNL Log Processing.cfg] 文件或任何 [!DNL Log Processing dataset include] 文件。 对于 [!DNL Transformation Field Viewer]，则可以添加 [!DNL Transformation.cfg] 文件或任何 [!DNL Transformation dataset include] 文件。

有关配置和包含文件的详细信息，请参阅《数据集配置指南》**。

## 添加和删除字段 {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**将字段添加到字段查看器**

* 在字段查看器中右键单击，然后单击 **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -或-

* 在字段查看器中右键单击现有列，然后单击 **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

“字段名称”指的是字段的名称，“实例”指的是使用其数据集配置中字段的位置，如数据集处理阶段或转换。某些字段会在数据集配置内的多处使用（例如，一个字段可由多个转换修改），因此您必须选择将哪个字段实例添加到字段查看器。

在可用字段的列表中，查看器内已显示的任意字段的左侧会显示一个 X。

**从字段查看器中删除字段**

* 右键单击要删除的字段的列，然后单击 **[!UICONTROL Remove Field]**.
