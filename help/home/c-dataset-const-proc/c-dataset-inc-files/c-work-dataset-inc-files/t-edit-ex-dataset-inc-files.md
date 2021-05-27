---
description: 编辑现有数据集包含文件的步骤。
title: 编辑现有数据集包含文件
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 37%

---

# 编辑现有数据集包含文件{#editing-existing-dataset-include-files}

编辑现有数据集包含文件的步骤。

使用Data Workbench中的[!DNL Profile Manager]打开一个现有数据集包含文件。

有关打开和使用[!DNL Profile Manager]的信息，请参阅&#x200B;*Data Workbench用户指南*。

1. 在数据集配置文件中工作时，打开[!DNL Profile Manager]并单击&#x200B;**[!UICONTROL Dataset]**&#x200B;以显示目录的内容。

   * 要打开[!DNL Log Processing Dataset Include]文件，请单击&#x200B;**[!UICONTROL Log Processing]**&#x200B;以显示目录的内容。

   * 要打开[!DNL Transformation Dataset Include]文件，请单击&#x200B;**[!UICONTROL Transformation]**&#x200B;以显示目录的内容。

1. 右键单击所需数据集包含文件旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。
1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此时会出现配置窗口。

   您还可以从[!DNL Transformation Dependency Maps]打开数据集包含文件。 有关[!DNL Transformation Dependency Maps]的信息，请参阅[重新处理和重新转换](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

1. 根据需要编辑配置文件中的参数。有关参数的描述，请参阅[日志处理数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)或[转换数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 。

   在 Data Workbench 窗口内编辑数据集包含文件时，可以使用快捷键实现基本编辑功能，包括剪切 (Ctrl+x)、复制 (Ctrl+c)、粘贴 (Ctrl+v)、撤消 (Ctrl+z)、恢复 (Ctrl+Shift+z)、选择部分（单击并拖动）以及选择全部 (Ctrl+a)。此外，您还可以使用快捷方式将文本从一个配置文件([!DNL .cfg])复制并粘贴到另一个配置文件。

1. 要保存更改，请右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。
1. 若要使本地所做的更改生效，请在[!DNL Profile Manager]列中右键单击[!DNL User]列中该文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*，其中“配置文件名称”是数据集包含文件所属的数据集配置文件或继承配置文件的名称。 在数据集配置文件同步之后，系统便会开始重新处理或重新转换数据。

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。
