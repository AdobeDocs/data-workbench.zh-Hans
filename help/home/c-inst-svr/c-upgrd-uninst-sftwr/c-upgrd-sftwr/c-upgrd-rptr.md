---
description: 使用Insight升级Repeater或通过复制文件进行升级的说明。
solution: Insight
title: 升级Repeater
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 升级Repeater{#upgrading-repeater}

使用Insight升级Repeater或通过复制文件进行升级的说明。

您可以使用以下方法之一从Platform 4.x或 [!DNL Repeater] 更高版本升级：

* 如果按照创建Insight和Repeater [!DNL Insight] 之间的连 [!DNL Repeater] 接中所述在和之间创建连接 [，则可以使用](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)进行升级 [!DNL Insight][!DNL Repeater]。 请参 [阅使用Insight升级Repeater](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)。

   -或-

* 如果无法或未在和之间创建连接， [!DNL Insight] 则 [!DNL Repeater]必须将升级文件直接复制到计算机 [!DNL Repeater] 上。 请参 [阅通过复制文件升级中继器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)。

## 使用Insight升级Repeater {#section-59c24448fd0f45c08abd0245ad746764}

1. 在计算 [!DNL Insight] 机上，将升级包中 [!DNL bin] 的文件夹复制到安 [!DNL Insight Server] 装目录中的 [!DNL Temp][!DNL Insight] 文件夹。
1. Start [!DNL Insight].
1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。
1. 右键单击要升级的 [!DNL Repeater] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]执行以下操作以将升级文件上传到服务器：

   1. 找到文 [!DNL bin] 件夹。
   1. 右键单击“临时”目录中文 [!DNL bin] 件夹的复选标记，然后选择 **[!UICONTROL Save Directory to]** > *&lt;&lt;**[!UICONTROL server name]**>*。

>[!NOTE]
>
>您将看到一条消息，指示此步骤覆盖服务器上存在的同名文件。 单击 **[!UICONTROL Yes]** 继续。

>[!NOTE]
>
>如果您需要上传其他文件以完成升 [!DNL Repeater] 级，Adobe将提供相关说明。

将升级文件上传到计算机后， [!DNL Repeater] 会自 [!DNL Repeater] 动重新启动并加载新版本。

## 通过复制文件升级Repeater {#section-202f2209f6604f19a15d96b517ea1bc1}

1. 打开Adobe提供的升级文件。 最可能的情况是，此文件是 [!DNL .zip] 用于升级的文 [!DNL Insight Server]件。
1. 转到您安装的目 [!DNL Repeater] 录(例如 [!DNL D:\Adobe\Repeater])。
1. 复制文 [!DNL bin] 件中的文 [!DNL .zip] 件夹并将其粘贴到安装目 [!DNL Repeater] 录中以覆盖现有的文 [!DNL bin] 件夹。

>[!NOTE]
>
>如果您需要上传其他文件以完成升 [!DNL Insight Server] 级，Adobe将提供相关说明。

将升级文件复制到计算机后，会自 [!DNL Repeater] 动重新启 [!DNL Repeater] 动它自己并加载新版本。
