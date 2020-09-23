---
description: 使用Insight升级Repeater或通过复制文件进行升级的说明。
solution: Analytics
title: 升级中继器
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# 升级中继器{#upgrading-repeater}

使用Insight升级Repeater或通过复制文件进行升级的说明。

您可以使用以下方法之一从Platform 4. [!DNL Repeater] x或更高版本升级：

* 如果按照创建Insight和 [!DNL Insight] Repeater [!DNL Repeater] 之间的连接 [中所述在之间创建连接](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)，则可以使用 [!DNL Insight] 进行升级 [!DNL Repeater]。 请参 [阅使用Insight升级Repeater](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)。

   -或-

* 如果无法或未在和之间创建连接， [!DNL Insight] 则 [!DNL Repeater]必须将升级文件直接复制到计算机 [!DNL Repeater] 上。 请参 [阅通过复制文件升级中继器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)。

## 使用Insight升级Repeater {#section-59c24448fd0f45c08abd0245ad746764}

1. 在计 [!DNL Insight] 算机上，将文 [!DNL bin] 件夹从升级包 [!DNL Insight Server] 复制到安 [!DNL Temp] 装目录中的 [!DNL Insight] 文件夹。
1. 开始 [!DNL Insight].
1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。
1. 右键单击要升级的 [!DNL Repeater] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]执行以下操作将升级文件上传到服务器：

   1. 找到文 [!DNL bin] 件夹。
   1. 右键单击Temp目录中文 [!DNL bin] 件夹的复选标记，然后选 **[!UICONTROL Save Directory to]** 择 *>**[!UICONTROL server name]**&lt;>*。

>[!NOTE]
>
>您将看到一条消息，指示此步骤覆盖服务器上存在的同名文件。 单击 **[!UICONTROL Yes]** 继续。

>[!NOTE]
>
>如果您需要上传其他文件以完 [!DNL Repeater] 成升级，Adobe将提供相关说明。

将升级文件上传到计算机 [!DNL Repeater] 后，自 [!DNL Repeater] 动重新启动并加载新版本。

## 通过复制文件升级Repeater {#section-202f2209f6604f19a15d96b517ea1bc1}

1. 打开由Adobe提供的升级文件。 很可能，此文件是用 [!DNL .zip] 于升级的文 [!DNL Insight Server]件。
1. 转到安装的目 [!DNL Repeater] 录(例如 [!DNL D:\Adobe\Repeater])。
1. 复制文 [!DNL bin] 件中的文 [!DNL .zip] 件夹并将其粘贴到安 [!DNL Repeater] 装目录中以覆盖现有文 [!DNL bin] 件夹。

>[!NOTE]
>
>如果您需要上传其他文件以完 [!DNL Insight Server] 成升级，Adobe将提供相关说明。

将升级文件复制到计算机 [!DNL Repeater] 后，自 [!DNL Repeater] 动重新启动并加载新版本。
