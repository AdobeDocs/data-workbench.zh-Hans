---
description: 可以将数据转换定义为在数据集构建的日志处理阶段或转换阶段应用。
title: 定义转换
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 63%

---

# 定义转换{#defining-a-transformation}

可以将数据转换定义为在数据集构建的日志处理阶段或转换阶段应用。

>[!NOTE]
>
>Adobe建议在[!DNL Log Processing]或[!DNL Transformation Dataset Include]文件中定义转换，而不是在[!DNL Log Processing.cfg]或[!DNL Transformation.cfg]中定义转换。

以下转换仅在[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件中定义时才有效：

* [AppendURI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)I
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC 数据源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**定义转换**

1. 使用[!DNL Profile Manager]打开要在其中定义转换的数据集配置文件。

   * （建议）要打开数据集包含文件，请参阅[数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。
   * 要打开[!DNL Log Processing.cfg]文件，请参阅[编辑日志处理配置文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * 要打开[!DNL Transformation.cfg]文件，请参阅[编辑转换配置文件](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

1. 右键单击&#x200B;**[!UICONTROL Transformations]**，然后单击&#x200B;**[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*。
1. 为转换输入适当的信息。有关转换类型的描述及其参数的信息，请参阅以下各节：

   * [标准转换](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI 转换](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [集成对照数据](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. 在配置文件中定义转换之后，将该文件保存在本地，然后将其保存到 Data Workbench Server 上的数据集配置文件中。

       定义和编辑转换的提示：
   
   * 在 Data Workbench 窗口内编辑转换的配置时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。此外，您还可以使用快捷键将文本或整个转换定义从一个配置文件([!DNL .cfg])复制并粘贴到另一个配置文件。
   * 对于您定义的任何转换，可以向 Comments（备注）参数中添加一个或多个备注行以进一步描述转换，也可以添加有关其用法的说明。要使用Data Workbench添加注释，请右键单击&#x200B;**[!UICONTROL Comments]**&#x200B;标签，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**。

   * 可以从[!DNL Transformation Dependency Map]打开任何转换的配置。 在打开配置之后，可以对其编辑并保存所做的更改。有关[!DNL Transformation Dependency Maps]的信息，请参阅[数据集配置工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

   * 从转换输出的空字符串会覆盖输出字段中的非空字符串。
