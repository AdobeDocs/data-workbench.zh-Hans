---
description: 创建新数据集包含文件的步骤。
title: 创建新数据集包含文件
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 42%

---

# 创建新数据集包含文件{#creating-new-dataset-include-files}

创建新数据集包含文件的步骤。

您应该创建新数据集包含文件来执行以下任意数据集配置任务：

* 指定要从日志处理过程传递到转换过程的新数据字段。
* 定义可执行以下任一操作的转换：

   * 更新现有日志字段。
   * 生成要从日志处理过程传递到转换过程或用于定义扩展维度的新字段。

      有关可用转换类型的信息，请参阅 [数据转换](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >如果要在新数据集包含文件中定义转换，请务必记住输入和输出的顺序。 有关转换顺序的信息，请参阅[构建转换的约定](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6)。

* 创建扩展维度。有关可用维度类型的信息，请参阅 [扩展维度](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. 在数据集用户档案中工作时，打开[!DNL Profile Manager]并单击&#x200B;**[!UICONTROL Dataset]**&#x200B;以视图现有数据集包含文件。

   * 要视图[!DNL Log Processing Dataset Include]文件，请单击&#x200B;**[!UICONTROL Log Processing]**。

   * 要视图[!DNL Transformation Dataset Include]文件，请单击&#x200B;**[!UICONTROL Transformation]**。

1. 通过执行以下步骤之一新建[!DNL Log Processing]或[!DNL Transformation Dataset Include]文件：

   * 在日志处理目录的[!DNL User]列中，单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**。 目录中将显示名为[!DNL New Log Processing.cfg]的文件。

   * 在Transformation目录的[!DNL User]列中，单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL New Transformation]**。 目录中将显示名为[!DNL New Transformation.cfg]的文件。

1. 在[!DNL User]列中右键单击新文件的复选标记，并在File参数中键入新名称，即可重命名新文件。

   ![步骤信息](assets/vis_ProfileManager_RenameFile.png)

1. 右键单击重命名的文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此时会出现配置窗口。
1. 根据需要编辑配置文件中的参数。有关可用参数的说明，请参阅[日志处理数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)或[转换数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。
1. 要保存更改，请右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。
1. 要使本地所做的更改生效，请在[!DNL Profile Manager]列中右键单击[!DNL User]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*，其中用户档案名称是数据集用户档案或数据集包含文件所属的继承用户档案的名称。 在数据集配置文件同步之后，系统便会开始重新处理或重新转换数据。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

要编辑您创建的数据集包含文件，请参阅[编辑现有数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。
