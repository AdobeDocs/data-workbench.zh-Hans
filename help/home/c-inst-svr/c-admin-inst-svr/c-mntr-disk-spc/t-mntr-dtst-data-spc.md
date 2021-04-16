---
description: 有关数据集监视和为数据集数据存储添加新位置的信息。
title: 监控数据集数据空间
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---

# 监控数据集数据空间{#monitoring-dataset-data-space}

有关数据集监视和为数据集数据存储添加新位置的信息。

**建议频率：** 每5-10分钟

默认情况下，[!DNL Insight Server]将其数据集写入数据处理单元上的[!DNL Insight Server]项目文件所在的驱动器上的[!DNL temp.db]文件。 每台[!DNL Insight Server]计算机的数据集数据量仅限于以下数据量（以先发生者为准）：

* 5亿（5亿）条数据输入数据
* 500 GB数据集数据存储
* 每个根级维度存储一(1)MB的数据集数据(例如，每个访客平均200字节，每个记录5,000条记录)

如果希望[!DNL Insight Server]在其他驱动器上维护数据集，或希望收集的数据量需要使用多个驱动器，则必须更新磁盘文件配置文件([!DNL Disk Files.cfg])以指定[!DNL Insight Server]写入[!DNL temp.db]文件的位置。 [!DNL Disk Files.cfg]文件列表磁盘文件（字符串的矢量），并指定在重新处理和操作过程中[!DNL Insight Server]使用的数据集数据的位置。 每个物理驱动器通常有一个文件。

>[!NOTE]
>
>在安装[!DNL Insight Server]时，可能已修改[!DNL Disk Files.cfg]文件的内容。 有关详细信息，请参阅[配置数据集的位置(temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)。

**为数据集数据存储添加新位置**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开Servers Manager工作区。
1. 右键单击要配置的[!DNL Insight Server]图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;视图其内容。 [!DNL Disk Files.cfg] 文件位于此目录中。
1. 右键单击[!DNL Disk Files.cfg]的&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Disk Files.cfg]的[!DNL Temp]列中显示复选标记。
1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Disk Files.cfg]窗口中，单击&#x200B;**[!UICONTROL component]**&#x200B;视图其内容。

   ![步骤信息](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >默认情况下，“检测磁盘损坏”参数设置为true。 “磁盘缓存大小(MB)”参数控制[!DNL Insight Server]用于提高磁盘访问速度的内存量，默认情况下将其设置为128。 请在更改其中任一参数之前与Adobe联系。

1. 要更改[!DNL Insight Server]计算机上的磁盘文件，请右键单击&#x200B;**[!UICONTROL Disk Files]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Disk File]**。

   要删除磁盘文件，请右键单击磁盘文件号，然后单击&#x200B;**[!UICONTROL Remove]**。

1. 对于新磁盘文件，输入在重新处理和操作过程中[!DNL Insight Server]要使用的文件的目录和名称。

   ![步骤信息](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >默认情况下，“检测磁盘损坏”参数设置为true。 “磁盘缓存大小(MB)”参数控制[!DNL Insight Server]用于提高磁盘访问速度的内存量，默认情况下将其设置为128。 请在更改其中任一参数之前与Adobe联系。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。
