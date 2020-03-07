---
description: 可以将数据转换定义为在数据集构建的日志处理阶段或转换阶段应用。
solution: Analytics
title: 定义转换
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 定义转换{#defining-a-transformation}

可以将数据转换定义为在数据集构建的日志处理阶段或转换阶段应用。

>[!NOTE]
>
>Adobe建议在或文件中定 [!DNL Log Processing] 义转 [!DNL Transformation Dataset Include] 换，而不是在或 [!DNL Log Processing.cfg] 中定义 [!DNL Transformation.cfg]。

The following transformations work only when defined in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file:

* [AppendURI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)I
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC 数据源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**定义转换**

1. Use the [!DNL Profile Manager] to open the dataset configuration file in which you want to define the transformation.

   * （推荐）要打开数据集包含文件，请参阅数 [据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。
   * 要打开文 [!DNL Log Processing.cfg] 件，请参阅 [编辑日志处理配置文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * 要打开文 [!DNL Transformation.cfg] 件，请参阅 [编辑转换配置文件](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

1. 右键单击， **[!UICONTROL Transformations]**&#x200B;然后单击 **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*。
1. 为转换输入适当的信息。有关转换类型的描述及其参数的信息，请参阅以下各节：

   * [标准转换](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI 转换](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [集成对照数据](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. 在配置文件中定义转换之后，将该文件保存在本地，然后将其保存到 Data Workbench Server 上的数据集配置文件中。

       定义和编辑转换的提示：
   
   * 在 Data Workbench 窗口内编辑转换的配置时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。In addition, you can use the shortcuts to copy and paste text or entire transformation definitions from one configuration file ( [!DNL .cfg]) to another.
   * 对于您定义的任何转换，可以向 Comments（备注）参数中添加一个或多个备注行以进一步描述转换，也可以添加有关其用法的说明。要使用Data Workbench添加评论，请右键单击标签， **[!UICONTROL Comments]** 然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**。

   * You can open the configuration of any transformation from a [!DNL Transformation Dependency Map]. 在打开配置之后，可以对其编辑并保存所做的更改。有关信息，请 [!DNL Transformation Dependency Maps]参阅数 [据集配置工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

   * 从转换输出的空字符串会覆盖输出字段中的非空字符串。

