---
description: 将数据集用户档案配置为在Insight Server群集上运行时，群集中的所有计算机共享该用户档案的所有数据集配置文件。
solution: Analytics
title: 将配置文件配置为在聚类上运行
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---


# 将配置文件配置为在聚类上运行{#configuring-a-profile-to-run-on-a-cluster}

将数据集用户档案配置为在Insight Server群集上运行时，群集中的所有计算机共享该用户档案的所有数据集配置文件。

因此，这些文件中参数的条目必须适用于群集中 [!DNL Insight Servers] 的所有参数。 例如，要读取的日志文件的位置、要使用的查找文件以及输出数据的位置 [!DNL Insight Server]在群集中的所有计算机 [!DNL Insight Server] 上必须相同。

您在群集的主控上执行所有配置任务, [!DNL Insight Server]即您用 [!DNL Insight Server] 来编辑配置文件的配置。 在主控上所做的所有保存的配置文件更 [!DNL Insight Server] 改都会自动同步到群集中处理中 [!DNL Insight Servers] 的文件中。

要在群集上运行数据集 [!DNL Insight Server] 用户档案，必须按列出的顺序执行以下进程：

1. [确定哪个Insight Server处理事件数据](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [在用户档案.cfg中指定处理服务器](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （如有必要） [修改用户档案的数据集配置文件](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## 确定哪个Insight Server处理事件数据 {#section-59b8e3f2b34f49739d544c8740a62fba}

群集进程中的所 [!DNL Insight Servers] 有事件数据不是必需的。 可以将群集中 [!DNL Insight Server] 的一个设备指定为文件服务器单元，以存储源文件(VSL和日志文件)并将文件提供给群集中的所有数据处理单元（处理服务器）。 此设置提供了单个事件数据存储库的优势，并利用了群集中所有处理服务器的处理能力。 处理服务器将数据文件分割，并保证同一文件不会多次处理。

有关指定将文件运 [!DNL Insight Server] 行为文件服务器单元的详细信息，请参阅《数据集配置指南》的“日志处理配 *置文件”一章*。

如果您决定将源数据文件存储在每个处理服务器上而不是单个文件服务器单元上，则必须在处理服务器之间平均划分这些文件。 请勿将数据集的所有源文件存储在每个处理服务器上。 如果同一文件的多个副本可用于多个处理服务器，则会多次读取数据（每台计算机一次）并使数据倾斜。

有关确定哪些日志文 [!DNL Insight Servers] 件应处理的帮助，请与Adobe咨询部门联系。

## 在用户档案.cfg中指定处理服务器 {#section-99664e072c21462f91fbafb6d893fcf9}

在文 [!DNL profile.cfg] 件中，指定处理用户档案数据的处理服务器。

**访问用户档案.cfg文件**

使用中访问用户档案配置 [!DNL Profile Manager] 文 [!DNL Insight]件。

1. 在数据集用户档案中工作时，在工 [!DNL Profile Manager] 作区中右键单击并单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > ，或打 **[!UICONTROL Profile Manager]**&#x200B;开用户档案管理工作区（在选项卡上） [!DNL Admin] 打开。

1. 在中， [!DNL Profile Manager]右键单击旁边的复选标记，然 [!DNL profile.cfg] 后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出现用户档案配置窗口。

**添加处理服务器**

1. 在文件 [!DNL profile.cfg] 中，单 **[!UICONTROL Profile]**&#x200B;击，然后单击 **[!UICONTROL Processing Servers]** 以显示其内容。

1. 右键单 **[!UICONTROL Processing Servers]** 击，然 **[!UICONTROL Add new]** 后单击 **[!UICONTROL Processing Server]**>。

1. 在“公用名称”参数中，键入群集中第一个处理服务器的公用名称。 例如：[!DNL server1.mycompany.com]
1. 重复步骤2和3，直到添加群集中所有处理服务器的公用名称。

   >[!NOTE]
   >
   >如果主控 [!DNL Insight Server] 处理数据，您还必须添加它。

1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

1. 右键单击旁边列中 [!DNL User] 的复选标记 [!DNL profile.cfg]。 单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## 修改用户档案的数据集配置文件 {#section-99bf9248e4e5483cb518f453b0a2f278}

**修改数据集配置文件**

如果需要更改数据集配置文件( [!DNL Log Processing.cfg]、 [!DNL Transformation.cfg]数据集包含文件 [!DNL Log Processing Mode.cfg]等)，请仅在主控进行更改 [!DNL Insight Server]。

1. 访问要修改的文件：

   有关访问文件的说明，请参阅《数据集 *配置指南》*。
1. 进行更改。有关配 *置文件中参数的详* 细信息，请参阅《数据集配置指南》。
1. 保存文件。

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 右键单击文件名旁 [!DNL User] 的列中的复选标记。
   1. 单击 **[!UICONTROL Save to]** 并选择所需的用户档案。

>[!NOTE]
>
>[!DNL Insight] 访问在群集上运行的数据集用户档案的用户只标识配 [!DNL Insight Server] 置文件( [!DNL Insight] )中的主控 [!DNL insight.cfg]项。 从用户的角 [!DNL Insight] 度来看，用户档案只能在一个 [!DNL Insight Server] 位置(主控 [!DNL Insight Server]);但是，分析师的查询请求可以定向到群 [!DNL Insight Servers] 集中的任意。

群 [!DNL Insight Server] 集允许（从）在 [!DNL .vsl] 称为文件服务器单 [!DNL Sensor]元(FSU)的单 [!DNL Insight Server] 台计算机上集中存储日志文件。 有关安装FSU的信息，请参 [阅Insight Server FSU的安装过程](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。 有关配置FSU的信息，请参阅《数据集配 *置指南》*。
