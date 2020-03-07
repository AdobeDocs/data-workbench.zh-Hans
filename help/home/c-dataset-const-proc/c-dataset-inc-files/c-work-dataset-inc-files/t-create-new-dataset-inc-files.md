---
description: 创建新数据集包含文件的步骤。
solution: Analytics
title: 创建新数据集包含文件
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 创建新数据集包含文件{#creating-new-dataset-include-files}

创建新数据集包含文件的步骤。

您应该创建新数据集包含文件来执行以下任意数据集配置任务：

* 指定要从日志处理过程传递到转换过程的新数据字段。
* 定义可执行以下任一操作的转换：

   * 更新现有日志字段。
   * 生成要从日志处理过程传递到转换过程或用于定义扩展维度的新字段。

      有关可用转换类型的信息，请参阅[数据转换](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

      >[!NOTE]
      >
      >如果要在新数据集包含文件中定义转换，请务必记住输入和输出的顺序。 有关转换顺序的信息，请参阅构 [建转换的约定](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6)。

* 创建扩展维度。有关可用维度类型的信息，请参阅 [Extended Dimensions（扩展维度）](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to view the existing dataset include files.

   * 要查看文 [!DNL Log Processing Dataset Include] 件，请单击 **[!UICONTROL Log Processing]**。

   * 要查看文 [!DNL Transformation Dataset Include] 件，请单击 **[!UICONTROL Transformation]**。

1. 通过执行以 [!DNL Log Processing] 下步 [!DNL Transformation Dataset Include] 骤之一创建新或文件：

   * 在“日 [!DNL User] 志处理”目录的列中，单击 **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**。 A file named [!DNL New Log Processing.cfg] appears in the directory.

   * 在“转 [!DNL User] 换”目录的列中，单击 **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**。 A file named [!DNL New Transformation.cfg] appears in the directory.

1. Rename the new file by right-clicking its check mark in the [!DNL User] column and typing the new name in the File parameter.

   ![步骤信息](assets/vis_ProfileManager_RenameFile.png)

1. Right-click the check mark for the renamed file and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 此时会出现配置窗口。
1. 根据需要编辑配置文件中的参数。有关可 [用参数的说明，请参阅日志处](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) 理数据集包含文件或转换数据集包含文件 [](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 。
1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs. 在数据集配置文件同步之后，系统便会开始重新处理或重新转换数据。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

要编辑您创建的数据集包含文件，请参阅编辑 [现有数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。
