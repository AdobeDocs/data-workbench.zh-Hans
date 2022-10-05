---
description: 有关添加、删除或复制条件的信息。
title: 使用条件
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 54%

---

# 使用条件{#working-with-conditions}

{{eol}}

有关添加、删除或复制条件的信息。

* [向数据集配置文件中添加条件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [从数据集配置文件中删除条件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [复制条件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## 向数据集配置文件中添加条件 {#section-3e2a34db047b462585502f69722f6511}

1. 在处理数据集配置文件时，请使用 [!DNL Profile Manager] 打开要编辑的数据集配置文件。

   * 要打开 [!DNL Log Processing.cfg] 文件，请参阅 [编辑日志处理配置文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * 要打开 [!DNL Transformation.cfg] 文件，请参阅 [编辑转换配置文件](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * 打开 [!DNL Dataset Include] 文件，请参阅 [数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. 在数据集配置文件内，找到要定义的 Log Entry Condition（日志条目条件）或 Condition（条件）参数。
1. 右键单击参数，然后单击 **[!UICONTROL Add new]**. 选择下列条件类型之一：

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. 根据需要编辑条件的参数。有关每种条件的参数描述，请参阅本附录的相应章节。
1. 要保存更改，请右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

1. 要使本地所做的更改生效，请在 [!DNL Profile Manager,] 右键单击 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>，其中profile name是数据集配置文件或该文件所属的继承配置文件的名称。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

## 从数据集配置文件中删除条件 {#section-677270f93f1648c3a268ca2aea7d4540}

1. 右键单击要删除的条件名称或对应的编号。
1. 单击 **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>，其中number是与要删除的条件对应的数字。

## 复制条件 {#section-00617bcf2c274f428686b2ec7f2d1db8}

您可以将条件从一个位置复制到同一文件中的另一个位置，或者从一个数据集配置文件复制到另一个数据集配置文件。

1. 右键单击要复制的条件的名称或对应的编号，然后单击 **[!UICONTROL Copy]**.
1. 右键单击要在其下放置复制条件的条件的名称或编号，然后单击 **[!UICONTROL Paste]**.
