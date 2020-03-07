---
description: 处理Insight Server与主Insight Server相同，但“组件”目录的内容除外。
solution: Insight
title: 安装和配置Processing Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装和配置Processing Insight Server{#installing-and-configuring-the-processing-insight-servers}

处理Insight Server与主Insight Server相同，但“组件”目录的内容除外。

处理中的“组件”目 [!DNL Insight Server] 录包含一组专门配置用于处理的特殊文件 [!DNL Insight Servers]。 这些文件从主服务器上的“处理服务器组件”目录中派生 [!DNL Insight Server]。

安装处理时，您 [!DNL Insight Server]需要执行以下操作来设置其“组件”目录：

1. 删除处理中的原始“组件”目录 [!DNL Insight Server]。
1. 将“处理服务器的组件”目录重命名为“组件”。
1. 在“组 [!DNL Synchronize.cfg] 件”目录中修改指向主视图的组件 [!DNL Insight Server]。

**安装和配置处理[!DNL Insight Server]**

1. 按照安 [!DNL Insight Server] 装Insight Server程序文件 [中所述安装程序文件](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)。 请确保复制在主设备上使用的目录结构 [!DNL Insight Server]。 例如，如果主 [!DNL Insight Server] 设备上安装 [!DNL C:\Adobe\Server] 了它， [!DNL Insight Server]则还必须在处理 [!DNL C:\Adobe\Server] 中安装它 [!DNL Insight Servers] 。
1. 安装Adobe为此特定处理颁发的数字证书 [!DNL Insight Server]。 有关 [说明，请参阅下载和安装数字证书](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) 。
1. 使用Windows资源管理器，在处理过程中执行以下操作 [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. 将文件夹重 [!DNL Components for Processing Servers] 命名为组件。

1. 使用文本编辑器（如记事本），在处 [!DNL Synchronize.cfg] 理过程中的“组件”目录中打开文件 [!DNL Insight Server]。
1. 将主（主）的IP地址添加 [!DNL Insight Server] 到此文件的第二行，如以下文件片段所示。 请勿编辑此文件中的任何其他内容。

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. 保存文件。
1. 按照将Insight [!DNL Insight Server] Server注册 [为Windows服务中所述启动](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

   您现在已完成群集的安 [!DNL Insight Server] 装。 接下来，按照以下部分所述，将数据集配置文件配置为在群集上运行。

