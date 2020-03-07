---
description: 有关数据集监视和为数据集数据存储添加新位置的信息。
solution: Insight
title: 监控数据集数据空间
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 监控数据集数据空间{#monitoring-dataset-data-space}

有关数据集监视和为数据集数据存储添加新位置的信息。

**推荐频率：** 每5-10分钟

默认情况下， [!DNL Insight Server] 将其数据集写入 [!DNL temp.db] 与数据处理单元上的程序文件 [!DNL Insight Server] 位于同一驱动器上的文件中。 每台计算机的数据集数 [!DNL Insight Server] 据量仅限于以下数据，以先发生者为准：

* 5亿（5亿）次数据输入记录
* 存储500(500)GB数据集数据
* 每个根级别维度存储一(1)MB的数据集数据（例如，每个访客5,000条记录，每条记录平均200字节）

如果要将数 [!DNL Insight Server] 据集维护在其他驱动器上，或者如果希望收集的数据量需要使用多个驱动器，则必须更新磁盘文件配置文件( [!DNL Disk Files.cfg])以指定要写入文 [!DNL Insight Server][!DNL temp.db] 件的位置。 该文 [!DNL Disk Files.cfg] 件列出磁盘文件（字符串矢量），并指定在重新处理和操作过程中使用的数据集 [!DNL Insight Server] 数据的位置。 通常每个物理驱动器有一个文件。

>[!NOTE]
>
>安装时可 [!DNL Disk Files.cfg] 能已修改文件内容 [!DNL Insight Server]。 有关详细信息，请 [参阅配置数据集的位置(temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)。

**为数据集数据存储添加新位置**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。
1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Disk Files.cfg] 文件位于此目录中。
1. Right-click the check mark in the *server name* column for [!DNL Disk Files.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Disk Files.cfg].
1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在窗 [!DNL Disk Files.cfg] 口中，单 **[!UICONTROL component]** 击以查看其内容。

   ![步骤信息](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >默认情况下，“检测磁盘损坏”参数设置为true。 “磁盘缓存大小(MB)”参数控制用于提高磁盘访问速 [!DNL Insight Server] 度的内存量，并且默认情况下设置为128。 在更改这些参数之一之前，请与Adobe联系。

1. 要更改计算机上的磁盘 [!DNL Insight Server] 文件，请右键单击并 **[!UICONTROL Disk Files]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**。

   要删除磁盘文件，请右键单击磁盘文件号并单击 **[!UICONTROL Remove]**。

1. 对于新磁盘文件，输入要在重新处理和操作过程中使用的文件的目 [!DNL Insight Server] 录和名称。

   ![步骤信息](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >默认情况下，“检测磁盘损坏”参数设置为true。 “磁盘缓存大小(MB)”参数控制用于提高磁盘访问速 [!DNL Insight Server] 度的内存量，并且默认情况下设置为128。 在更改这些参数之一之前，请与Adobe联系。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记，然 [!DNL Temp] 后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

