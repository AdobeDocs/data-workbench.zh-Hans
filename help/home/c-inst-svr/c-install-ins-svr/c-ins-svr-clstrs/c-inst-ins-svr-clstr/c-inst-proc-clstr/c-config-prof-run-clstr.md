---
description: 当您将数据集配置文件配置为在Insight Server群集上运行时，群集中的所有计算机共享该配置文件的所有数据集配置文件。
title: 将配置文件配置为在聚类上运行
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# 将配置文件配置为在聚类上运行{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

当您将数据集配置文件配置为在Insight Server群集上运行时，群集中的所有计算机共享该配置文件的所有数据集配置文件。

因此，这些文件中参数的条目必须适用于所有 [!DNL Insight Servers] 在群集中。 例如，要读取的日志文件的位置、要使用的查找文件 [!DNL Insight Server]，以及输出数据的位置 [!DNL Insight Server] 群集中所有计算机上必须相同。

在群集的主控上执行所有配置任务 [!DNL Insight Server]，这是 [!DNL Insight Server] 用于编辑配置文件。 所有保存的配置文件在主控上发生更改 [!DNL Insight Server] 自动同步到处理中的文件 [!DNL Insight Servers] 在群集中。

在 [!DNL Insight Server] 群集时，必须按所列顺序执行以下进程：

1. [确定哪些Insight Server处理事件数据](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [在Profile.cfg中指定处理服务器](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （如有必要） [修改配置文件的数据集配置文件](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## 确定哪些Insight Server处理事件数据 {#section-59b8e3f2b34f49739d544c8740a62fba}

并非所有 [!DNL Insight Servers] 在群集进程事件数据中。 您可以指定一个 [!DNL Insight Server] 作为文件服务器单元(用于存储源文件(VSL和日志文件)，并将文件提供给群集中的所有数据处理单元（处理服务器）)。 此设置提供单个事件数据存储库的好处，并利用群集中所有处理服务器的处理能力。 处理服务器将数据文件分割，并保证同一文件不会被多次处理。

有关指定 [!DNL Insight Server] 要以文件服务器单元的形式运行，请参阅 *数据集配置指南*.

如果决定将源数据文件存储在每个处理服务器上，而不是存储在单个文件服务器单元上，则必须在处理服务器之间平均划分这些文件。 请勿将数据集的所有源文件存储在每个处理服务器上。 如果同一文件的多个副本可用于多个处理服务器，则数据会被多次读取（每台计算机一次），并会影响数据的准确性。

帮助确定 [!DNL Insight Servers] 应处理日志文件，请联系Adobe咨询。

## 在Profile.cfg中指定处理服务器 {#section-99664e072c21462f91fbafb6d893fcf9}

在 [!DNL profile.cfg] 文件中，指定用于处理配置文件数据的处理服务器。

**访问profile.cfg文件**

使用 [!DNL Profile Manager] in [!DNL Insight].

1. 在处理数据集配置文件时，打开 [!DNL Profile Manager] 右键单击工作区并单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**，或在 [!DNL Admin] 选项卡。

1. 在 [!DNL Profile Manager]，右键单击旁边的复选标记 [!DNL profile.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。

1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 出现配置文件配置窗口。

**添加处理服务器**

1. 在 [!DNL profile.cfg] 文件，单击 **[!UICONTROL Profile]**，然后单击 **[!UICONTROL Processing Servers]** 以显示其内容。

1. 右键单击 **[!UICONTROL Processing Servers]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. 在Common Name参数中，键入群集中第一个处理服务器的通用名称。 例如：[!DNL server1.mycompany.com]
1. 重复步骤2和3，直到添加群集中所有处理服务器的通用名称。

   >[!NOTE]
   >
   >如果主控 [!DNL Insight Server] 处理数据时，您还必须添加该数据。

1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

1. 右键单击 [!DNL User] 列旁边 [!DNL profile.cfg]. 单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## 修改配置文件的数据集配置文件 {#section-99bf9248e4e5483cb518f453b0a2f278}

**修改数据集配置文件**

如果您需要更改数据集配置文件( [!DNL Log Processing.cfg], [!DNL Transformation.cfg]，数据集包含文件， [!DNL Log Processing Mode.cfg]，等等)，则仅在主控上执行此操作 [!DNL Insight Server].

1. 访问要修改的文件：

   有关访问文件的说明，请参阅 *数据集配置指南*.
1. 进行更改。请参阅 *数据集配置指南* 有关配置文件中参数的详细信息。
1. 保存文件。

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 右键单击 [!DNL User] 列。
   1. 单击 **[!UICONTROL Save to]** ，然后选择所需的配置文件。

>[!NOTE]
>
>[!DNL Insight] 访问在群集上运行的数据集配置文件的用户仅标识主控 [!DNL Insight Server] 在 [!DNL Insight] 配置文件( [!DNL insight.cfg])。 从 [!DNL Insight] 用户，则只能在一个 [!DNL Insight Server] (主控 [!DNL Insight Server]);但是，分析人员的查询请求可以定向到任何 [!DNL Insight Servers] 在群集中。

安 [!DNL Insight Server] 群集允许将 [!DNL .vsl] 日志文件(从 [!DNL Sensor]) [!DNL Insight Server] 称为文件服务器单元(FSU)的计算机。 有关安装FSU的信息，请参阅 [Insight Server FSU的安装过程](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). 有关配置FSU的信息，请参阅 *数据集配置指南*.
