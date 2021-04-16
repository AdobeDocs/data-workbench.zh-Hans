---
description: Data Workbench可以配置为仅允许特定用户更改特定工作区。
title: 配置锁定的工作区
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 55%

---

# 配置锁定的工作区{#configure-a-locked-workspace}

Data Workbench可以配置为仅允许特定用户更改特定工作区。

当工作区锁定时，用户可以在大多数可视化中进行选择并且可以对表格中的数据进行排序，但是不能更改工作区。此功能可防止用户对工作区进行误更改。

以下三个元素必须一起使用才能控制工作区的锁定：

* **文件夹.lock或工 *作区名*称.lock文件：文** 件指 [!DNL folder.lock] 定是否锁定特定文件夹中的工作区，而工作区 [!DNL name.lock] 文件指定是否锁定特定工作区。

* **用户 [!DNL Insight.cfg] 文件中的 Unlock（解锁）参数：**&#x200B;此参数指定用户是否可以对锁定的工作区临时解锁。
* **“临时解锁”菜单选项：**&#x200B;当用户 [!DNL Insight.cfg] 中的 Unlock（解锁）参数设置为 true 时，该选项会自动显示在每个锁定工作区的标题栏菜单中，以便为用户提供解锁方法。

有关[!DNL folder.lock]和工作区[!DNL name.lock]文件的信息，请参见下一节。 有关设置Unlock（解锁）参数的信息，请参阅[设置Unlock（解锁）参数](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)。 有关[!DNL Temporarily Unlock menu]选项的信息，请参阅[解锁工作区](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)。
