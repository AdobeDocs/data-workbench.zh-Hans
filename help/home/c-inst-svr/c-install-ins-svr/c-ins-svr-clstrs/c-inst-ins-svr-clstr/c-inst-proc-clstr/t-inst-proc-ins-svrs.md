---
description: 处理Insight Server与主控Insight Server相同，但其“组件”目录的内容除外。
solution: Analytics
title: 安装和配置 Insight Server 的处理方法
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---


# 安装和配置 Insight Server 的处理方法{#installing-and-configuring-the-processing-insight-servers}

处理Insight Server与主控Insight Server相同，但其“组件”目录的内容除外。

处理中的“组件”目 [!DNL Insight Server] 录包含一组专门配置用于处理的特殊文件 [!DNL Insight Servers]。 这些文件从主控上的“处理服务器的组件”目录派生 [!DNL Insight Server]。

安装处理时， [!DNL Insight Server]请执行以下操作以设置其“组件”目录：

1. 删除处理中的原始“组件”目录 [!DNL Insight Server]。
1. 将“处理服务器的组件”目录重命名为“组件”。
1. 修改“ [!DNL Synchronize.cfg] 组件”目录中的指向主控 [!DNL Insight Server]。

**安装和配置处理[!DNL Insight Server]**

1. 按照安 [!DNL Insight Server] 装Insight Server项目文 [件中的说明安装项目文件](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)。 确保重复主控上使用的目录结构 [!DNL Insight Server]。 例如，如果 [!DNL Insight Server] 在主控 [!DNL C:\Adobe\Server] 中安装， [!DNL Insight Server]则还必须在处理 [!DNL C:\Adobe\Server] 中安装 [!DNL Insight Servers] 它。
1. 安装Adobe为此特定处理颁发的数字证书 [!DNL Insight Server]。 有关 [说明，请参阅下载和安装](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) “数字证书”。
1. 使用Windows资源管理器，在处理过程中执行以下操作 [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. 将文件夹重 [!DNL Components for Processing Servers] 命名为组件。

1. 使用文本编辑器（如记事本），在 [!DNL Synchronize.cfg] 处理过程中的组件目录中打开文件 [!DNL Insight Server]。
1. 将主控（主）的IP地址添 [!DNL Insight Server] 加到此文件的第二行，如以下文件片段所示。 请勿编辑此文件中的任何其他内容。

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
1. 开始 [!DNL Insight Server] ，如将 [Insight Server注册为Windows服务中所述](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

   您现在已完成群集的安 [!DNL Insight Server] 装。 接下来，按照以下部分所述，将数据集用户档案配置为在群集上运行。

