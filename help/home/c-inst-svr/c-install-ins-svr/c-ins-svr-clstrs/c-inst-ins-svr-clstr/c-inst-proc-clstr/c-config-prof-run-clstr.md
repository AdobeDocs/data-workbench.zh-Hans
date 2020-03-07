---
description: 将数据集配置文件配置为在Insight Server群集上运行时，群集中的所有计算机共享该配置文件的所有数据集配置文件。
solution: Insight
title: 配置要在群集上运行的配置文件
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置要在群集上运行的配置文件{#configuring-a-profile-to-run-on-a-cluster}

将数据集配置文件配置为在Insight Server群集上运行时，群集中的所有计算机共享该配置文件的所有数据集配置文件。

因此，这些文件中参数的条目必须适用于群集中 [!DNL Insight Servers] 的所有参数。 例如，要读取的日志文件的位置、要使用的查找文件以及输出数据的位置在群集中的所有计算机上 [!DNL Insight Server][!DNL Insight Server] 必须相同。

您可以在群集的主服务器上执行所有配 [!DNL Insight Server]置任务，该任务是 [!DNL Insight Server] 用于编辑配置文件的任务。 在主设备上所做的所有保存的配置文件更 [!DNL Insight Server] 改都会自动同步到群集中处理时的 [!DNL Insight Servers] 文件中。

要在群集上运行数据集配 [!DNL Insight Server] 置文件，您必须按列出的顺序执行以下进程：

1. [确定哪个Insight Server处理事件数据](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [在Profile.cfg中指定处理服务器](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （如有必要） [修改配置文件的数据集配置文件](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## 确定哪个Insight Server处理事件数据 {#section-59b8e3f2b34f49739d544c8740a62fba}

群集中的所有事件数 [!DNL Insight Servers] 据不一定都要处理。 您可以将群集中 [!DNL Insight Server] 的一个文件服务器单元指定为文件服务器单元，用于存储源文件（VSL和日志文件），并将文件提供给群集中的所有数据处理单元（处理服务器）。 此设置提供了单个事件数据存储库的优势，并利用了群集中所有处理服务器的处理能力。 处理服务器在它们之间分割数据文件，并保证同一文件不会多次被处理。

有关指定运行为文件服 [!DNL Insight Server] 务器单元的详细信息，请参阅《数据集配置指南》的“日志处理配置文 *件”一章*。

如果您决定将源数据文件存储在每台处理服务器上而不是单个文件服务器单元上，则必须在处理服务器之间平均分配这些文件。 请勿在每个处理服务器上存储数据集的所有源文件。 如果同一文件的多个副本可用于多个处理服务器，则会多次读取数据（每台计算机一次）并使数据倾斜。

有关确定应处理 [!DNL Insight Servers] 日志文件的帮助信息，请与Adobe Consulting联系。

## 在Profile.cfg中指定处理服务器 {#section-99664e072c21462f91fbafb6d893fcf9}

在文件 [!DNL profile.cfg] 中，指定处理配置文件数据的处理服务器。

**访问profile.cfg文件**

使用中访问配置文件配 [!DNL Profile Manager] 置文件 [!DNL Insight]。

1. 在处理数据集配置文件时，在工作区中 [!DNL Profile Manager] 右键单击并单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > ，或打开选项卡上的“配置文件管理”工作 **[!UICONTROL Profile Manager]**[!DNL Admin] 区以打开。

1. 在中， [!DNL Profile Manager]右键单击旁边的复选标记并单 [!DNL profile.cfg] 击鼠标 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出现配置文件配置窗口。

**添加处理服务器**

1. 在文件 [!DNL profile.cfg] 中，单击 **[!UICONTROL Profile]**，然后单击 **[!UICONTROL Processing Servers]** 以显示其内容。

1. 右键单击 **[!UICONTROL Processing Servers]** 并单击 **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**。

1. 在“公用名”参数中，键入群集中第一个处理服务器的公用名。 例如：[!DNL server1.mycompany.com]
1. 重复第2步和第3步，直到添加群集中所有处理服务器的通用名称。

   >[!NOTE]
   >
   >如果主处 [!DNL Insight Server] 理数据，您还必须添加它。

1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

1. 右键单击旁边列中的 [!DNL User] 复选标记 [!DNL profile.cfg]。 单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## 修改配置文件的数据集配置文件 {#section-99bf9248e4e5483cb518f453b0a2f278}

**修改数据集配置文件**

如果需要更改数据集配置文件( [!DNL Log Processing.cfg]、 [!DNL Transformation.cfg]、数据集包含文件 [!DNL Log Processing Mode.cfg]等)，请仅在主设备上进行更改 [!DNL Insight Server]。

1. 访问要修改的文件：

   有关访问文件的说明，请参阅《数据集配 *置指南》*。
1. 进行更改。有关配 *置文件中参数的详细信息* ，请参阅《数据集配置指南》。
1. 保存文件。

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 右键单击文件名旁 [!DNL User] 的列中的复选标记。
   1. 单击 **[!UICONTROL Save to]** 并选择所需的配置文件。

>[!NOTE]
>
>[!DNL Insight] 访问在群集上运行的数据集配置文件的用户只标识配置 [!DNL Insight Server] 文件( [!DNL Insight] )中的主 [!DNL insight.cfg]视图。 从用户的角度 [!DNL Insight] 看，只有一个人（主人）可访 [!DNL Insight Server] 问配置文件 [!DNL Insight Server];但是，分析师的查询请求可以定向到群集中 [!DNL Insight Servers] 的任意一个。

群集 [!DNL Insight Server] 允许（从）在称为文件服 [!DNL .vsl] 务器单元(FSU)的 [!DNL Sensor][!DNL Insight Server] 单台计算机上集中存储日志文件。 有关安装FSU的信息，请参 [阅Insight Server FSU的安装过程](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。 有关配置FSU的信息，请参阅《数据集配 *置指南》*。
