---
description: 定义扩展维度的步骤。
title: 定义扩展维度
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 57%

---

# 定义扩展维度{#defining-extended-dimensions}

{{eol}}

定义扩展维度的步骤。

1. 在处理数据集配置文件时，打开 [!DNL Profile Manager] 单击 **[!UICONTROL Dataset]** 以显示其内容。
1. 打开 [!DNL Transformation.cfg] 文件或 [!DNL Transformation Dataset Include] 要在其中定义扩展维度的文件。

   * （推荐）要打开数据集包含文件，请参阅 [数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe建议在一个或多个新维度中定义扩展维度 [!DNL Transformation Dataset Include] 文件。 有关更多信息，请参阅 [创建新数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

   * 要打开 [!DNL Transformation.cfg] 文件，请参阅 [编辑转换配置文件](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. 右键单击 **[!UICONTROL Transformations]** 单击 **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. 为扩展维度输入相应信息。有关转换类型的描述及其参数的信息，请参阅以下各节：

   * [可计数维度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [简单维度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [多对多维度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [数值维度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [非正规维度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [时间维度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      对于您定义的任何扩展维度，可以向 Comments（备注）参数中添加一个或多个备注行以进一步描述维度，也可以添加有关其用法的说明。要添加评论，请右键单击 **[!UICONTROL Comments]** 标签，单击 **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. 在配置文件中定义扩展维度之后，将该文件保存在本地，然后将其保存到 Data Workbench Server 上的数据集配置文件中。
