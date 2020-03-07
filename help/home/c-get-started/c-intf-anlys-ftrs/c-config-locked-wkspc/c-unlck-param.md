---
description: 用户 Insight.cfg 文件中的 Unlock（解锁）参数指定用户是否有权对锁定的工作区临时解锁以进行编辑。
solution: Analytics
title: 设置unlock参数
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Set the unlock parameter{#set-the-unlock-parameter}

用户 Insight.cfg 文件中的 Unlock（解锁）参数指定用户是否有权对锁定的工作区临时解锁以进行编辑。

If the Unlock parameter is already present in the user’s [!DNL Insight.cfg] file, you can edit the parameter using Data Workbench. 如果用户的 [!DNL Insight.cfg] 文件中不存在该参数，则必须使用文本编辑器（例如记事本）将其添加到该文件中。

**[!DNL Unlock]在 Insight.cfg 文件中设置现有 （解锁）参数**

1. 在工作区中，右键单击 **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**。 The [!DNL Insight.cfg] file opens.
1. 对于 Unlock（解锁）参数，键入 true 或 false。True 表示允许用户暂时对任何锁定的工作区解锁，而 false 则不允许。
1. 要保存配置更改，请右键单击 **[!UICONTROL Insight.cfg (modified)]** 窗口顶部的按钮，然后单击 **[!UICONTROL Save as Insight.cfg]**。

**将 Unlock（解锁）参数添加到 Insight.cfg 文件**

1. Navigate to your Data Workbench installation directory and open the [!DNL Insight.cfg] file using a text editor, such as Notepad.
1. 将 Unlock（解锁）参数添加到文件末尾，如下例所示：

[!DNL Unlock = bool: false]

1. 设置值为 true 或 false。True 表示允许用户暂时对任何锁定的工作区解锁，而 false 则不允许。
1. 保存并关闭该文件。

