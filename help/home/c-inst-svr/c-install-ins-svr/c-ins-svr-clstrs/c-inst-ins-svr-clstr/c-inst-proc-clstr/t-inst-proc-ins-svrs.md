---
description: 处理Insight Server与主控Insight Server相同，但其Components目录的内容除外。
title: 安装和配置 Insight Server 的处理方法
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# 安装和配置 Insight Server 的处理方法{#installing-and-configuring-the-processing-insight-servers}

处理Insight Server与主控Insight Server相同，但其Components目录的内容除外。

处理[!DNL Insight Server]上的Components目录包含一组专门配置用于处理[!DNL Insight Servers]的特殊文件。 这些文件是从主控[!DNL Insight Server]上的Components for Processing Servers目录派生的。

安装处理[!DNL Insight Server]时，请执行以下操作以设置其Components目录：

1. 删除处理[!DNL Insight Server]中的原始“组件”目录。
1. 将“处理服务器的组件”目录重命名为“组件”。
1. 修改Components目录中的[!DNL Synchronize.cfg]以指向主控[!DNL Insight Server]。

**安装和配置处理[!DNL Insight Server]**

1. 按照[安装Insight Server项目文件](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)中所述安装[!DNL Insight Server]项目文件。 请务必重复主控[!DNL Insight Server]上使用的目录结构。 例如，如果[!DNL Insight Server]安装在主控[!DNL Insight Server]的[!DNL C:\Adobe\Server]中，则还必须将它安装在处理[!DNL Insight Servers]的[!DNL C:\Adobe\Server]中。
1. 安装Adobe为此特定处理颁发的[!DNL Insight Server]数字证书。 有关说明，请参见[下载和安装数字证书](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 使用Windows资源管理器，对处理[!DNL Insight Server]执行以下操作：

   1. 删除&#x200B;**[!UICONTROL Components]**&#x200B;文件夹。
   1. 将[!DNL Components for Processing Servers]文件夹重命名为组件。

1. 使用文本编辑器（如记事本），打开处理[!DNL Insight Server]的Components目录中的[!DNL Synchronize.cfg]文件。
1. 将主控（主）[!DNL Insight Server]的IP地址添加到此文件的第二行，如以下文件片段所示。 请勿编辑此文件中的任何其他内容。

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
1. 开始[!DNL Insight Server]，如[将Insight Server注册为Windows服务](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)中所述。

   您现在已完成[!DNL Insight Server]群集的安装。 接下来，按照以下部分所述，配置要在群集上运行的数据集用户档案。
