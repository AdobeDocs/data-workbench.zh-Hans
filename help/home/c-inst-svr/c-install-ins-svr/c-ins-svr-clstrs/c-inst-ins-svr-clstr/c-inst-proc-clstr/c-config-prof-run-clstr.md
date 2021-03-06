---
description: 当您将数据集配置文件配置为在Insight Server群集上运行时，群集中的所有计算机共享该配置文件的所有数据集配置文件。
title: 将配置文件配置为在聚类上运行
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# 将配置文件配置为在聚类上运行{#configuring-a-profile-to-run-on-a-cluster}

当您将数据集配置文件配置为在Insight Server群集上运行时，群集中的所有计算机共享该配置文件的所有数据集配置文件。

因此，这些文件中参数的条目必须适用于群集中的所有[!DNL Insight Servers]。 例如，要读取的日志文件、[!DNL Insight Server]要使用的查找文件以及[!DNL Insight Server]输出的数据的位置在群集中的所有计算机上都必须相同。

您在群集的主控[!DNL Insight Server]（用于编辑配置文件的[!DNL Insight Server]）上执行所有配置任务。 在主控[!DNL Insight Server]上所做的所有保存的配置文件更改都会自动同步到群集中处理[!DNL Insight Servers]上的文件。

要在[!DNL Insight Server]群集上运行数据集配置文件，必须按所列顺序执行以下进程：

1. [确定哪些Insight Server处理事件数据](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [在Profile.cfg中指定处理服务器](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （如有必要）[修改配置文件的数据集配置文件](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## 确定哪些Insight Server处理事件数据{#section-59b8e3f2b34f49739d544c8740a62fba}

集群处理事件数据中的所有[!DNL Insight Servers]并非必需的。 您可以在群集中指定一个[!DNL Insight Server]作为文件服务器单元，用于存储源文件(VSL和日志文件)并将文件提供给群集中的所有数据处理单元（处理服务器）。 此设置提供单个事件数据存储库的好处，并利用群集中所有处理服务器的处理能力。 处理服务器将数据文件分割，并保证同一文件不会被多次处理。

有关指定[!DNL Insight Server]以作为文件服务器单元运行的详细信息，请参阅《数据集配置指南》*中的“日志处理配置文件”一章。*

如果决定将源数据文件存储在每个处理服务器上，而不是存储在单个文件服务器单元上，则必须在处理服务器之间平均划分这些文件。 请勿将数据集的所有源文件存储在每个处理服务器上。 如果同一文件的多个副本可用于多个处理服务器，则数据会被多次读取（每台计算机一次），并会影响数据的准确性。

有关确定哪个[!DNL Insight Servers]应处理日志文件的帮助，请联系Adobe咨询。

## 在Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}中指定处理服务器

在[!DNL profile.cfg]文件中，指定用于处理配置文件数据的处理服务器。

**访问profile.cfg文件**

使用[!DNL Insight]中的[!DNL Profile Manager]访问配置文件配置文件。

1. 在处理数据集配置文件时，通过右键单击工作区并单击&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**，或打开[!DNL Admin]选项卡上的“配置文件管理”工作区来打开[!DNL Profile Manager]。

1. 在[!DNL Profile Manager]中，右键单击[!DNL profile.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。

1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出现配置文件配置窗口。

**添加处理服务器**

1. 在[!DNL profile.cfg]文件中，单击&#x200B;**[!UICONTROL Profile]**，然后单击&#x200B;**[!UICONTROL Processing Servers]**&#x200B;以显示其内容。

1. 右键单击&#x200B;**[!UICONTROL Processing Servers]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**。

1. 在Common Name参数中，键入群集中第一个处理服务器的通用名称。 例如：[!DNL server1.mycompany.com]
1. 重复步骤2和3，直到添加群集中所有处理服务器的通用名称。

   >[!NOTE]
   >
   >如果主控[!DNL Insight Server]处理数据，则还必须添加该数据。

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

1. 右键单击[!DNL profile.cfg]旁边[!DNL User]列中的复选标记。 单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## 修改配置文件{#section-99bf9248e4e5483cb518f453b0a2f278}的数据集配置文件

**修改数据集配置文件**

如果您需要更改数据集配置文件（[!DNL Log Processing.cfg]、[!DNL Transformation.cfg]、数据集包含文件、[!DNL Log Processing Mode.cfg]等），请仅在主控的[!DNL Insight Server]上进行更改。

1. 访问要修改的文件：

   有关访问文件的说明，请参阅&#x200B;*《数据集配置指南》*。
1. 进行更改。有关配置文件中参数的详细信息，请参阅&#x200B;*数据集配置指南*。
1. 保存文件。

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 右键单击文件名旁边[!DNL User]列中的复选标记。
   1. 单击&#x200B;**[!UICONTROL Save to]**&#x200B;并选择所需的配置文件。

>[!NOTE]
>
>[!DNL Insight] 访问在群集上运行的数据集配置文件的用户只识别配置 [!DNL Insight Server] 文件( [!DNL Insight]  [!DNL insight.cfg])中的主控。从[!DNL Insight]用户的角度来看，配置文件只能在一个[!DNL Insight Server](主控[!DNL Insight Server])上访问；但是，可以将分析师的查询请求定向到群集中的任何[!DNL Insight Servers]。

[!DNL Insight Server]群集允许将[!DNL .vsl]日志文件（从[!DNL Sensor]）集中存储到名为文件服务器单元(FSU)的单台[!DNL Insight Server]计算机上。 有关安装FSU的信息，请参阅[Insight Server FSU的安装过程](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。 有关配置FSU的信息，请参阅&#x200B;*《数据集配置指南》*。
