---
description: 可以将Data Workbench配置为仅允许特定用户更改特定工作区。
solution: Analytics
title: 配置锁定的工作区
topic: Data workbench
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置锁定的工作区{#configure-a-locked-workspace}

可以将Data Workbench配置为仅允许特定用户更改特定工作区。

当工作区锁定时，用户可以在大多数可视化中进行选择并且可以对表格中的数据进行排序，但是不能更改工作区。此功能可防止用户对工作区进行误更改。

以下三个元素必须一起使用才能控制工作区的锁定：

* **文件夹。lock或工&#x200B;*作区名称*.lock文件：** 文件 [!DNL folder.lock] 指定是否锁定特定文件夹中的工作区，而工作区文件指定 [!DNL name.lock] 是否锁定特定工作区。

* **用户[!DNL Insight.cfg]文件中的 Unlock（解锁）参数：**&#x200B;此参数指定用户是否可以对锁定的工作区临时解锁。
* **“临时解锁”菜单选项：**&#x200B;当用户 [!DNL Insight.cfg] 中的 Unlock（解锁）参数设置为 true 时，该选项会自动显示在每个锁定工作区的标题栏菜单中，以便为用户提供解锁方法。

For information about [!DNL folder.lock] and workspace [!DNL name.lock] files, see the following section. 有关设置Unlock（解锁）参数的信息，请参 [阅设置Unlock（解锁）参数](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)。 有关此选项的信 [!DNL Temporarily Unlock menu] 息，请参 [阅解锁工作区](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)。
