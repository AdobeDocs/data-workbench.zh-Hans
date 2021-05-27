---
description: Worktop 中的每个选项卡或子选项卡都对应一种特定的信息类型，例如“功能板”、“活动”、“获取”，等等。
title: 自定义工作台选项卡
uuid: f1f557c8-f4cb-4789-8162-39cc7c52c943
exl-id: 529c6d8d-fc42-4c2b-a111-b8eea4665d8b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 66%

---

# 自定义工作台选项卡{#customize-a-worktop-tab}

Worktop 中的每个选项卡或子选项卡都对应一种特定的信息类型，例如“功能板”、“活动”、“获取”，等等。

例如，[!DNL Acquisition]选项卡可能包含提供有关反向链接域、搜索引擎和促销活动数据的工作区。

[!DNL Worktop]中显示的每个选项卡都与&#x200B;*工作配置文件名称*\Workspaces文件夹中位于Data Workbench安装目录内的文件夹相对应。 [!DNL Worktop] 中选项卡的顺序由相同文件夹中的 [!DNL order.txt] 文件来控制。例如，如果在 Workspaces 文件夹中有一个 子文件夹，然后在 [!DNL order.txt] 文件中添加 作为第一个条目，则“[!DNL Acquisition]获取”即是 [!DNL Worktop] 中的第一个选项卡，该子文件夹下的所有内容将显示在“[!DNL Acquisition]获取”选项卡中。

>[!NOTE]
>
>有关使用[!DNL order.txt]文件自定义工作区窗口菜单的信息，请参阅[自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/c-ctm-menus.md#concept-93d4c09cb7f34cd293b7b64fba1cf894)。
