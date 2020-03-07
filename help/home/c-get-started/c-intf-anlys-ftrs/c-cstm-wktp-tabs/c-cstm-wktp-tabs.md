---
description: Worktop 中的每个选项卡或子选项卡都对应一种特定的信息类型，例如“功能板”、“活动”、“获取”，等等。
solution: Analytics
title: 自定义Worktop选项卡
topic: Data workbench
uuid: f1f557c8-f4cb-4789-8162-39cc7c52c943
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 自定义Worktop选项卡{#customize-a-worktop-tab}

Worktop 中的每个选项卡或子选项卡都对应一种特定的信息类型，例如“功能板”、“活动”、“获取”，等等。

For example, the [!DNL Acquisition] tab might contain workspaces that provide data about referring domains, search engines, and campaigns.

Each tab that appears in the [!DNL Worktop] corresponds to a folder in the *working profile name*\Workspaces folder within the Data Workbench installation directory. [!DNL Worktop] 中选项卡的顺序由相同文件夹中的 [!DNL order.txt] 文件来控制。例如，如果在 Workspaces 文件夹中有一个 子文件夹，然后在 [!DNL order.txt] 文件中添加 作为第一个条目，则“[!DNL Acquisition]获取”即是 [!DNL Worktop] 中的第一个选项卡，该子文件夹下的所有内容将显示在“[!DNL Acquisition]获取”选项卡中。

>[!NOTE]
>
>For information about using the [!DNL order.txt] file to customize the workspace window menu, see [Customizing Menus](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/c-ctm-menus.md#concept-93d4c09cb7f34cd293b7b64fba1cf894).

