---
description: 编辑现有数据集包含文件的步骤。
solution: Analytics
title: 编辑现有数据集包含文件
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 编辑现有数据集包含文件{#editing-existing-dataset-include-files}

编辑现有数据集包含文件的步骤。

You open an existing dataset include file using the [!DNL Profile Manager] in data workbench.

For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*.

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show the contents of the directory.

   * 要打开文 [!DNL Log Processing Dataset Include] 件，请单 **[!UICONTROL Log Processing]** 击以显示目录的内容。

   * 要打开文 [!DNL Transformation Dataset Include] 件，请单 **[!UICONTROL Transformation]** 击以显示目录的内容。

1. Right-click the check mark next to the desired dataset include file and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此时会出现配置窗口。

   You can also open a dataset include file from a [!DNL Transformation Dependency Maps]. 有关信息，请 [!DNL Transformation Dependency Maps]参阅重新 [处理和重新转换](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

1. 根据需要编辑配置文件中的参数。有关 [参数的说明，请参阅日志处理数](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) 据集包含文件或转换数据集包含文件 [](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 。

   在 Data Workbench 窗口内编辑数据集包含文件时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs. 在数据集配置文件同步之后，系统便会开始重新处理或重新转换数据。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

