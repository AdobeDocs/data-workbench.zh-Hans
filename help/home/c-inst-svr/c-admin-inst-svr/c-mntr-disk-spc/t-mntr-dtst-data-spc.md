---
description: 有关数据集监控和为数据集数据存储添加新位置的信息。
title: 监控数据集数据空间
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---

# 监控数据集数据空间{#monitoring-dataset-data-space}

{{eol}}

有关数据集监控和为数据集数据存储添加新位置的信息。

**推荐频率：** 每5-10分钟

默认情况下， [!DNL Insight Server] 将其数据集写入 [!DNL temp.db] 文件与 [!DNL Insight Server] 数据处理单元上的程序文件。 每个数据集数据量 [!DNL Insight Server] 计算机受以下限制（以先发生者为准）：

* 5亿（5亿）条数据输入到该数据集的记录
* 存储了500(500)GB的数据集数据
* 每个根级别维度存储一(1)MB的数据集数据（例如，每个访客5,000条记录，每条记录平均200字节）

如果您需要 [!DNL Insight Server] 要在其他驱动器上维护数据集，或者如果要收集的数据量需要使用多个驱动器，则必须更新磁盘文件配置文件( [!DNL Disk Files.cfg])指定您想要的位置 [!DNL Insight Server] 写 [!DNL temp.db] 文件。 的 [!DNL Disk Files.cfg] 文件会列出磁盘文件（字符串矢量），并指定使用的数据集数据的位置 [!DNL Insight Server] 在重新处理和操作期间。 每个物理驱动器通常有一个文件。

>[!NOTE]
>
>的内容 [!DNL Disk Files.cfg] 文件可能在安装时被修改 [!DNL Insight Server]. 有关更多信息，请参阅 [配置数据集(temp.db)的位置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**为数据集数据存储添加新位置**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。
1. 右键单击 [!DNL Insight Server] 要配置并单击 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Components]** 查看其内容。 [!DNL Disk Files.cfg] 文件位于此目录中。
1. 右键单击 *服务器名称* 列 [!DNL Disk Files.cfg] 单击 **[!UICONTROL Make Local]**. 在 [!DNL Temp] 列 [!DNL Disk Files.cfg].
1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL Disk Files.cfg] 窗口，单击 **[!UICONTROL component]** 查看其内容。

   ![步骤信息](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >默认情况下， Detect Disk Croruption（检测磁盘损坏）参数设置为true。 磁盘缓存大小(MB)参数控制 [!DNL Insight Server] 用于提高磁盘访问速度，默认情况下设置为128。 在更改其中任一参数之前，请联系Adobe。

1. 更改 [!DNL Insight Server] 计算机，右键单击 **[!UICONTROL Disk Files]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   要删除磁盘文件，请右键单击磁盘文件号，然后单击 **[!UICONTROL Remove]**.

1. 对于新磁盘文件，输入要使用的文件的目录和名称 [!DNL Insight Server] 在重新处理和操作期间。

   ![步骤信息](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >默认情况下， Detect Disk Croruption（检测磁盘损坏）参数设置为true。 磁盘缓存大小(MB)参数控制 [!DNL Insight Server] 用于提高磁盘访问速度，默认情况下设置为128。 在更改其中任一参数之前，请联系Adobe。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，右键单击 [!DNL Temp] 列和选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
