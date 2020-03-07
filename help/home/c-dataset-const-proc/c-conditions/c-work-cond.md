---
description: 有关添加、删除或复制条件的信息。
solution: Analytics
title: 使用条件
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 使用条件{#working-with-conditions}

有关添加、删除或复制条件的信息。

* [向数据集配置文件中添加条件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [从数据集配置文件中删除条件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [复制条件](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## 向数据集配置文件中添加条件 {#section-3e2a34db047b462585502f69722f6511}

1. While working in your dataset profile, use the [!DNL Profile Manager] to open the dataset configuration file that you want to edit.

   * 要打开文 [!DNL Log Processing.cfg] 件，请参阅 [编辑日志处理配置文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * 要打开文 [!DNL Transformation.cfg] 件，请参阅 [编辑转换配置文件](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

   * 要打开文件， [!DNL Dataset Include] 请参阅数 [据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 在数据集配置文件内，找到要定义的 Log Entry Condition（日志条目条件）或 Condition（条件）参数。
1. 右键单击该参数，然后单击 **[!UICONTROL Add new]**。 选择下列条件类型之一：

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. 根据需要编辑条件的参数。有关每种条件的参数描述，请参阅本附录的相应章节。
1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager,] right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, where profile name is the name of the dataset profile or the inherited profile to which the file belongs.

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

## 从数据集配置文件中删除条件 {#section-677270f93f1648c3a268ca2aea7d4540}

1. 右键单击要删除的条件名称或对应的编号。
1. Click **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, where number is the number corresponding to the condition that you want to remove.

## 复制条件 {#section-00617bcf2c274f428686b2ec7f2d1db8}

您可以将条件从一个位置复制到同一文件中的另一个位置，或者从一个数据集配置文件复制到另一个数据集配置文件。

1. Right-click the name of the condition or the number corresponding to the condition that you want to copy and click **[!UICONTROL Copy]**.
1. Right-click the name or number of the condition below which you want to place the copied condition and click **[!UICONTROL Paste]**.

