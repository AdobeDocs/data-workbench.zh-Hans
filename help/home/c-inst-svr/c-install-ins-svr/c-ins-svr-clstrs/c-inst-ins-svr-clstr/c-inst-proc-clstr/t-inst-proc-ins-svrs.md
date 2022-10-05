---
description: 处理的Insight Server与主控的Insight Server相同，但其“组件”目录的内容除外。
title: 安装和配置 Insight Server 的处理方法
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# 安装和配置 Insight Server 的处理方法{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

处理的Insight Server与主控的Insight Server相同，但其“组件”目录的内容除外。

处理过程中的Components目录 [!DNL Insight Server] 包含专门配置用于处理的特殊文件集 [!DNL Insight Servers]. 这些文件是从主控上的Components for Processing Server目录派生的 [!DNL Insight Server].

安装处理时 [!DNL Insight Server]，请执行以下操作以设置其Components目录：

1. 删除处理中的原始Components目录 [!DNL Insight Server].
1. 将“处理服务器的组件”目录重命名为“组件”。
1. 修改 [!DNL Synchronize.cfg] （位于组件目录中）以指向主控 [!DNL Insight Server].

**安装和配置处理[!DNL Insight Server]**

1. 安装 [!DNL Insight Server] 程序文件，如 [安装Insight Server程序文件](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). 请确保复制在主控上使用的目录结构 [!DNL Insight Server]. 例如，如果 [!DNL Insight Server] 安装在 [!DNL C:\Adobe\Server] 关于主控 [!DNL Insight Server]，则必须在 [!DNL C:\Adobe\Server] 处理时 [!DNL Insight Servers] 也是。
1. 安装Adobe为此特定处理颁发的数字证书 [!DNL Insight Server]. 请参阅 [下载并安装数字证书](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) 中。
1. 使用Windows资源管理器，在处理过程中执行以下操作 [!DNL Insight Server]:

   1. 删除 **[!UICONTROL Components]** 文件夹。
   1. 重命名 [!DNL Components for Processing Servers] 文件夹到组件。

1. 使用文本编辑器（如记事本），打开 [!DNL Synchronize.cfg] 文件（位于处理时的Components目录中） [!DNL Insight Server].
1. 添加主控（主）的IP地址 [!DNL Insight Server] 到此文件的第二行，如以下文件片段中所示。 请勿编辑此文件中的任何其他内容。

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
1. 启动 [!DNL Insight Server] 如 [将Insight Server注册为Windows服务](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   您现在已完成 [!DNL Insight Server] 群集。 接下来，按照以下部分所述，将数据集配置文件配置为在群集上运行。
