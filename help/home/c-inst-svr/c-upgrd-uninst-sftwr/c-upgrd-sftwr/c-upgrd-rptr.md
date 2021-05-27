---
description: 有关使用Insight升级中继器或通过复制文件进行升级的说明。
title: 升级中继器
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 升级中继器{#upgrading-repeater}

有关使用Insight升级中继器或通过复制文件进行升级的说明。

您可以使用以下方法之一从Platform 4.x或更高版本升级[!DNL Repeater]:

* 如果您按照[创建Insight与中继器之间的连接](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)中所述在[!DNL Insight]和[!DNL Repeater]之间创建连接，则可以使用[!DNL Insight]升级[!DNL Repeater]。 请参阅[使用Insight升级中继器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)。

   -或-

* 如果无法或未在[!DNL Insight]和[!DNL Repeater]之间创建连接，则必须将升级文件直接复制到[!DNL Repeater]计算机。 请参阅[通过复制文件升级中继器](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)。

## 使用Insight {#section-59c24448fd0f45c08abd0245ad746764}升级中继器

1. 在[!DNL Insight]计算机上，将[!DNL bin]文件夹从[!DNL Insight Server]升级包复制到[!DNL Insight]安装目录的[!DNL Temp]文件夹中。
1. 开始 [!DNL Insight].
1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。
1. 右键单击要升级的[!DNL Repeater]图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，执行以下操作以将升级文件上传到服务器：

   1. 找到[!DNL bin]文件夹。
   1. 右键单击Temp目录中[!DNL bin]文件夹的复选标记，然后选择&#x200B;**[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*。

>[!NOTE]
>
>您将看到一条消息，指示此步骤将覆盖服务器上存在的同名文件。 单击&#x200B;**[!UICONTROL Yes]**&#x200B;继续。

>[!NOTE]
>
>如果您需要上传其他文件以完成[!DNL Repeater]升级，Adobe将提供相关说明。

将升级文件上载到[!DNL Repeater]计算机后，[!DNL Repeater]会自动重新启动并加载新版本。

## 通过复制文件{#section-202f2209f6604f19a15d96b517ea1bc1}来升级中继器

1. 打开由Adobe提供的升级文件。 此文件很可能是用于升级[!DNL Insight Server]的[!DNL .zip]文件。
1. 转到安装[!DNL Repeater]的目录（例如[!DNL D:\Adobe\Repeater]）。
1. 复制[!DNL .zip]文件中的[!DNL bin]文件夹，并将其粘贴到[!DNL Repeater]安装目录中，以覆盖现有的[!DNL bin]文件夹。

>[!NOTE]
>
>如果您需要上传其他文件以完成[!DNL Insight Server]升级，Adobe将提供相关说明。

将升级文件复制到[!DNL Repeater]计算机后，[!DNL Repeater]会自动重新启动并加载新版本。
