---
description: 有关使用Insight升级中继器或通过复制文件进行升级的说明。
title: 升级中继器
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 升级中继器{#upgrading-repeater}

{{eol}}

有关使用Insight升级中继器或通过复制文件进行升级的说明。

您可以使用以下方法之一进行升级 [!DNL Repeater] 从Platform 4.x或更高版本：

* 如果您在 [!DNL Insight] 和 [!DNL Repeater] 如 [在Insight与中继器之间创建连接](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)，您可以使用 [!DNL Insight] 升级 [!DNL Repeater]. 请参阅 [使用Insight升级中继器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -或-

* 如果无法或未在 [!DNL Insight] 和 [!DNL Repeater]，则必须将升级文件直接复制到 [!DNL Repeater] 机器。 请参阅 [通过复制文件升级中继器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## 使用Insight升级中继器 {#section-59c24448fd0f45c08abd0245ad746764}

1. 在 [!DNL Insight] 计算机，复制 [!DNL bin] 文件夹 [!DNL Insight Server] 将包升级到 [!DNL Temp] 文件夹，其中 [!DNL Insight] 已安装。
1. 开始 [!DNL Insight].
1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。
1. 右键单击 [!DNL Repeater] 要升级，请单击 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，请执行以下操作以将升级文件上传到服务器：

   1. 找到 [!DNL bin] 文件夹。
   1. 右键单击 [!DNL bin] 文件夹，然后选择 **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>您将看到一条消息，指示此步骤将覆盖服务器上存在的同名文件。 单击 **[!UICONTROL Yes]** 继续。

>[!NOTE]
>
>如果您需要上传其他文件以完成 [!DNL Repeater] 升级时，Adobe将提供相关说明。

将升级文件上传到 [!DNL Repeater] 机器， [!DNL Repeater] 会自动重新启动自身并加载新版本。

## 通过复制文件升级中继器 {#section-202f2209f6604f19a15d96b517ea1bc1}

1. 打开由Adobe提供的升级文件。 很可能，此文件是 [!DNL .zip] 升级文件 [!DNL Insight Server].
1. 转到安装的目录 [!DNL Repeater] (例如， [!DNL D:\Adobe\Repeater])。
1. 复制 [!DNL bin] 文件夹 [!DNL .zip] 并将其粘贴到 [!DNL Repeater] 用于覆盖现有 [!DNL bin] 文件夹。

>[!NOTE]
>
>如果您需要上传其他文件以完成 [!DNL Insight Server] 升级时，Adobe将提供相关说明。

将升级文件复制到 [!DNL Repeater] 机器， [!DNL Repeater] 会自动重新启动自身并加载新版本。
