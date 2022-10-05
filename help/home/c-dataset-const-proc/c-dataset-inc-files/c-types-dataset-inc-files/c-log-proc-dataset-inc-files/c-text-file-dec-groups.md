---
description: 若要将日志文件处理为日志源，需要在日志处理数据集包含文件中定义解码器，以从日志条目中提取数据字段。
title: 文本文件解码器组
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
exl-id: e9f6e02e-7150-455f-96f0-f34d98cc31b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 68%

---

# 文本文件解码器组{#text-file-decoder-groups}

{{eol}}

若要将日志文件处理为日志源，需要在日志处理数据集包含文件中定义解码器，以从日志条目中提取数据字段。

为日志文件日志源定义文本文件解码器组需要了解日志文件的结构和内容、要提取的数据以及将存储数据的字段。本节提供了您可以为解码器指定的参数的基本描述，但您使用任何解码器的方式取决于包含源数据的日志文件。

有关日志文件日志源的格式要求的信息，请参阅[日志文件](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)。在定义文本文件解码器时如需帮助，请联系 Adobe。

文本文件解码器组可包括：

* [正则表达式解码器](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [分隔解码器](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## 正则表达式解码器 {#section-67aca2c1f008404da7f845a64abec97c}

正则表达式解码器可在日志文件的日志条目中识别复杂的字符串模式，并将这些模式提取为数据字段。对于每个解码器，字段数量都必须等于正则表达式中捕获子模式的数量。与第 n 个捕获子模式匹配的行部分会分配给该行的第 n 个字段。

**向文本文件解码器组中添加正则表达式解码器**

1. 打开 [!DNL Log Processing Dataset Include] 文件，如 [编辑现有数据集包含文件](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) 和添加文本文件解码器组。 请参阅表条目 [解码器组](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. 右键单击 **[!UICONTROL Decoders]** 在新创建的解码器组下，单击 **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. 指定以下信息：

   * **字段：**&#x200B;日志文件中的字段列表。如果此处定义的任何字段要传递到数据集构建的转换阶段，则这些字段必须列在 [!DNL Log Processing Dataset Include] 数据集的文件。 自定义字段名称必须以“x-”开头。

   * **名称：**&#x200B;解码器的可选标识符。
   * **正则表达式：**&#x200B;用于从文件中的每一行提取所需的字段。

1. 对于您想要添加到组中的任何其他解码器重复第 4 步和第 5 步。
1. 保存 [!DNL Log Processing Dataset Include] 文件，右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

1. 要使本地所做的更改生效，请在 [!DNL Profile Manager]，右键单击 [!DNL User] 列。 单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*，其中“配置文件名称”是数据集配置文件或数据集包含文件所属的继承配置文件的名称。

请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

>[!NOTE]
>
>给定的日志文件可以具有多个正则表达式解码器。 定义解码器的顺序很重要：与日志文件中某一行匹配的第一个解码器是用于对该行进行解码的解码器。

此示例说明了如何使用正则表达式解码器从以制表符分隔的文本文件中提取数据字段。您可以通过使用制表分隔符定义分隔解码器来达到相同的效果。

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

有关正则表达式解码器的详细信息（包括术语和语法），请参阅 [正则表达式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## 分隔解码器 {#section-7e0a23decdbc4c75ae750a42446997a6}

分隔解码器会对其字段用单个字符分隔的日志文件进行解码。字段数量必须与分隔文件中的列数量相对应；但是，并非所有字段都需要命名。如果某个字段保留为空，则日志文件中仍将需要有对应的列，但解码器会忽略该列。

**向文本文件解码器组中添加分隔解码器**

1. 打开 [!DNL Log Processing Dataset Include] 文件，如 [编辑现有数据集包含文件](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) 和添加文本文件解码器组。 请参阅表条目 [解码器组](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. 右键单击 **[!UICONTROL Decoders]** 在新创建的解码器组下，单击 **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. 指定以下信息：

   * **字段：**&#x200B;日志文件中的字段列表。如果此处定义的任何字段要传递到数据集构建的转换阶段，则这些字段必须列在 [!DNL Log Processing Dataset Include] 数据集的文件。 自定义字段名称必须以“x-”开头。

   * **分隔符：**&#x200B;在输出文件中用于分隔字段的字符。

1. 对于您想要添加到组中的任何其他解码器重复第 4 步和第 5 步。
1. 保存 [!DNL Log Processing Dataset Include] 文件，右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

1. 要使本地所做的更改生效，请在 [!DNL Profile Manager]，右键单击 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*，其中“配置文件名称”是数据集配置文件或数据集包含文件所属的继承配置文件的名称。

>[!NOTE]
>
>请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

此示例说明了如何使用分隔解码器从包含电影相关数据的逗号分隔文本文件中提取数据字段。

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)
